# Section 2: How to setup a Practice Lab

Section 2 explains how to build a small practice lab for Active Directory and hybrid identity work. The lab is useful for understanding how an on-premises domain connects to cloud identity later in the course, but most SC-300 topics can still be studied with a normal computer, a browser, and cloud-based simulations.

> [!NOTE]
> This section is lab-focused. Key terms link to the [SC-300 glossary](../00-front-matter/glossary.md) on first meaningful use.

## 13. Introduction to Building a Practice Lab

### Core idea

The practice lab gives you a safe place to work with virtual machines, Windows Server, [Active Directory Domain Services](../00-front-matter/glossary.md#active-directory-domain-services), and Microsoft Entra synchronization concepts before touching any real environment.

### What to know

- The lab is most useful for hands-on practice with AD DS and Microsoft Entra Connect-style hybrid identity.
- You can complete many SC-300 topics without local virtual machines.
- A normal Windows or macOS computer with a browser is enough for many cloud-only lessons and simulations.
- Hyper-V requires Windows Pro, Enterprise, or Education. Windows Home does not include full Hyper-V support.
- VirtualBox or VMware can be alternatives, but the section assumes Hyper-V.

### Lab purpose

| Lab component | Why it matters |
|---|---|
| Windows Server VM | Hosts AD DS and becomes the [domain controller](../00-front-matter/glossary.md#domain-controller) |
| Windows client VM | Joins the domain and validates domain sign-in |
| Virtual switch | Connects the VMs to the network |
| Microsoft 365 / Azure tenant | Supports later cloud and hybrid identity practice |

> [!TIP]
> Memory hook: The lab exists to make hybrid identity real. Cloud-only topics do not always require local VMs.

## 14. Downloading a Windows Server 2022 ISO

### Core idea

A Windows Server ISO is the installation media used to create the server VM that will later become the domain controller.

### What to know

- Download Windows Server installation media from Microsoft or another trusted official source.
- Save the ISO somewhere easy to find, such as a local downloads or lab media folder.
- Keep the ISO outside the repository. Installation media should not be committed to GitHub.
- Windows Server with Desktop Experience is easier for this beginner lab than Server Core.

### Evidence to add

When documenting your own lab later, record the server version, edition, and VM name you used. Do not include product keys, private account information, or screenshots with personal data.

> [!WARNING]
> Exam trap: An ISO is only installation media. It does not create the domain, install AD DS, or configure identity by itself.

## 15. Getting Hyper-V Installed on Windows

### Core idea

Hyper-V is Microsoft’s built-in virtualization platform for running local virtual machines on supported Windows editions.

### What to know

- Hyper-V is available on supported Windows Pro, Enterprise, and Education editions.
- Hardware virtualization must be enabled and supported by the computer.
- The required Windows features are Hyper-V Platform and Hyper-V Management Tools.
- A reboot is normally required after enabling Hyper-V.
- Hyper-V Manager is the primary GUI used in this lab.

### Key concepts

| Concept | Study-guide meaning |
|---|---|
| Hyper-V Platform | The virtualization components that run VMs |
| Hyper-V Management Tools | Administrative tools such as Hyper-V Manager |
| Hardware virtualization | CPU support that allows the host to run virtual machines efficiently |
| Host computer | The physical computer running Hyper-V |
| Guest VM | The virtual machine running inside Hyper-V |

> [!WARNING]
> Exam trap: Installing Hyper-V Manager alone is not enough. The Hyper-V Platform must also be enabled for VMs to run.

## 16. Creating a Virtual Switch in Hyper-V

### Core idea

A virtual switch connects virtual machines to a network. For this lab, an external virtual switch lets the VMs reach the same outside network as the host computer.

### What to know

- A virtual switch behaves like a software-based network switch.
- An external switch binds to a physical network adapter, such as Wi-Fi or Ethernet.
- VMs connected to the external switch can usually reach the internet through the host network.
- Creating or changing a virtual switch may briefly interrupt host network connectivity.

### Virtual switch types

| Switch type | Purpose | Common lab use |
|---|---|---|
| External | Connects VMs to the physical network through a host adapter | Internet access and domain lab connectivity |
| Internal | Allows communication between VMs and the host only | Isolated host-and-VM testing |
| Private | Allows communication between VMs only | Fully isolated VM-to-VM testing |

> [!TIP]
> Memory hook: External reaches out, internal reaches the host, private stays between VMs.

## 17. Installing a Windows Server 2022 Virtual Machine

### Core idea

The Windows Server VM becomes the foundation of the on-premises side of the lab. It will later be renamed, configured for DNS, and promoted to a domain controller.

### What to know

- Use a clear VM name, such as a lab domain controller name.
- Generation 2 is preferred for modern Windows Server VMs.
- 4 GB of memory is a reasonable minimum for a small lab VM.
- Connect the VM to the external virtual switch.
- Install from the Windows Server ISO.
- Disable checkpoints if you want a simpler lab state and fewer unexpected rollbacks.

### Recommended lab settings

| Setting | Suggested value | Why it matters |
|---|---|---|
| Generation | Generation 2 | Modern firmware and security support |
| Memory | 4096 MB | Enough for a basic GUI-based lab server |
| Dynamic Memory | Off | Keeps memory behavior predictable while learning |
| Network | External virtual switch | Allows internet and lab network connectivity |
| Disk | Default dynamic virtual disk | Fine for a temporary study lab |
| Edition | Desktop Experience | Easier for beginner GUI-based setup |

> [!WARNING]
> Exam trap: Server Core is valid in real environments, but Desktop Experience is easier for a foundational learning lab.

## 18. Downloading the Windows 11 ISO

### Core idea

The Windows 11 ISO provides the installation media for the Windows client VM. The client VM is used to test [domain join](../00-front-matter/glossary.md#domain-join), DNS configuration, and domain sign-in.

### What to know

- Download Windows 11 installation media from Microsoft or another trusted official source.
- Choose a language and 64-bit edition appropriate for your lab.
- Store the ISO locally and keep it out of the GitHub repository.
- Portal and download-page layouts can change, so focus on obtaining a valid ISO rather than memorizing one screen.

### Evidence to add

For later documentation, record the Windows 11 version, VM name, and whether it successfully joined the domain. Avoid publishing personal sign-in information or machine-specific private details.

## 19. Installing a Windows 11 Virtual Machine

### Core idea

The Windows 11 VM acts as the domain-joined client. It verifies whether the domain controller, DNS, and domain authentication are working correctly.

### What to know

- Use Generation 2 for modern Windows 11 VMs when supported.
- Enable virtual TPM for Windows 11 requirements.
- Assign at least two virtual processors.
- Use 4 GB of memory or more for a smoother lab experience.
- Connect the VM to the same virtual switch as the server VM.
- Use the domain-join or local-account flow during setup if you do not want to sign in with a Microsoft account.

### Required VM settings

| Setting | Suggested value | Notes |
|---|---|---|
| Generation | Generation 2 | Recreate as Generation 1 only if hardware or boot issues require it |
| Memory | 4096 MB or higher | More memory improves the install experience |
| Processor | 2 or more virtual CPUs | Windows 11 installation is smoother with multiple vCPUs |
| TPM | Enabled | Required for a normal Windows 11 VM install |
| Network | External virtual switch | Keeps the client on the same lab network |

> [!TIP]
> Memory hook: The server proves identity services work; the client proves users and devices can consume them.

## 20. Disable Large Send Offload Version 2

### Core idea

Large Send Offload can sometimes cause slow or unreliable network behavior after enabling Hyper-V. Disabling Large Send Offload v2 on the host’s Hyper-V virtual Ethernet adapter can fix certain lab connectivity issues.

### What to know

- This troubleshooting step is performed on the host computer, not inside the VM.
- The relevant adapter is usually a Hyper-V virtual Ethernet adapter.
- Disable Large Send Offload v2 for both IPv4 and IPv6 if the lab network becomes slow or unstable.
- This is a practical lab fix, not a replacement for understanding DNS, routing, or firewall issues.

### Troubleshooting scope

| Symptom | Possible action |
|---|---|
| Internet becomes very slow after Hyper-V is enabled | Check the Hyper-V virtual Ethernet adapter settings |
| VM network access drops intermittently | Disable Large Send Offload v2 for IPv4 and IPv6 |
| Domain join fails | Check DNS first, not Large Send Offload first |

> [!WARNING]
> Exam trap: Large Send Offload is a host networking performance feature. Domain join and authentication failures are more commonly caused by DNS or connectivity problems.

## 21. Setting up a Domain Controller

### Core idea

The Windows Server VM becomes a domain controller after it is renamed, pointed to itself for DNS, installed with AD DS, and promoted into a new [forest](../00-front-matter/glossary.md#forest).

### What to know

- Rename the server before promotion so the domain controller has a clean, meaningful name.
- Configure preferred DNS to the loopback address or the server’s own IP before promotion.
- Install the AD DS role through Server Manager or PowerShell.
- Promote the server to a domain controller and create a new forest for the lab.
- Keep DNS and [Global Catalog](../00-front-matter/glossary.md#global-catalog) enabled for a basic first domain controller.
- Use sanitized lab names in public notes instead of publishing real domains.

### Process overview

| Step | Purpose |
|---:|---|
| 1 | Rename the server | Gives the future domain controller a clear identity |
| 2 | Configure DNS | Ensures the server can resolve domain services correctly |
| 3 | Install AD DS | Adds the directory service role |
| 4 | Promote the server | Turns the server into a domain controller |
| 5 | Create a new forest | Builds the first domain in the lab environment |
| 6 | Reboot and verify | Confirms domain, DNS, and AD tools are available |

### Domain controller concepts

| Concept | Study-guide meaning |
|---|---|
| Forest | The top-level AD DS security and configuration boundary |
| Domain | The logical identity boundary created inside the forest |
| Global Catalog | A searchable catalog of directory objects used for logon and lookup scenarios |
| [DSRM](../00-front-matter/glossary.md#dsrm) password | Recovery password used for Directory Services Restore Mode |
| [NetBIOS name](../00-front-matter/glossary.md#netbios-name) | Legacy short domain name used for backward compatibility |
| [SYSVOL](../00-front-matter/glossary.md#sysvol) | Shared folder structure used by domain controllers for scripts and Group Policy data |
| [SRV records](../00-front-matter/glossary.md#srv-record) | DNS records that help clients locate domain services |

### Verification

After promotion, verify the lab before moving on:

- Server Manager shows the expected domain.
- DNS contains a forward lookup zone for the lab domain.
- `_tcp` and `_udp` SRV records exist.
- Active Directory Users and Computers is available.
- The server can resolve its own domain services.

> [!WARNING]
> Exam trap: The domain controller must be discoverable through DNS. A server can have AD DS installed but still fail clients if DNS is wrong.

> [!TIP]
> Memory hook: Rename, DNS, install AD DS, promote, reboot, verify.

## 22. Joining Windows 11 to a Domain

### Core idea

The Windows 11 VM joins the domain by using the domain controller as its DNS server, reaching the domain controller across the network, and authenticating with domain credentials.

### What to know

- The client must use the domain controller for DNS.
- The client must be able to reach the domain controller’s IP address.
- Rename the client to a clear lab name before or during domain join.
- Use domain administrator or delegated domain credentials to join the device.
- After restart, sign in with a domain account to confirm the join worked.

### Process overview

| Step | Purpose |
|---:|---|
| 1 | Identify the domain controller IP | Needed for client DNS configuration |
| 2 | Set client DNS to the domain controller | Allows the client to locate the domain |
| 3 | Rename the Windows 11 VM | Keeps lab devices organized |
| 4 | Verify connectivity | Confirms the client can reach the domain controller |
| 5 | Join the domain | Registers the client as a domain-joined computer |
| 6 | Sign in as a domain user | Confirms domain authentication works |

### Validation commands

Use basic checks before joining the domain:

```powershell
ipconfig /all
ping <domain-controller-ip>
```

The DNS server shown on the client should be the domain controller, not a public DNS resolver.

> [!WARNING]
> Exam trap: If the Windows 11 client uses public DNS, it will not find the private AD DS domain. Domain join depends on the client querying the domain controller’s DNS service.

> [!TIP]
> Memory hook: Domain join usually fails at discovery before it fails at credentials. Check DNS first.
