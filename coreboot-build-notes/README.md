# Build notes for coreboot

## Steps for connecting to #xorg-devel IRC: [Freenode registration steps](https://freenode.net/kb/answer/registration)

1. Register nickname by sending this message on IRC: /msg NickServ REGISTER password youremail@example.com

Note: Registration is one time. The nickname may expire after long time of no use.

2. Identify your nickname by sending this message on IRC: /msg NickServ IDENTIFY foo password

3. In case you forgot password, to reset your password send this message on IRC: /msg NickServ SENDPASS nickname

## Names of packages in Fedora (to that of mentioned in the documentation (ubuntu based)

Package name on Ubuntu | Package name in Fedora
--- | --- 
zlib1g-dev | zlib-devel
gnat | gcc-gnat

## Problems I faced while building [coreboot](https://www.coreboot.org/) 

--- 

## coreboot stages (as per wikipedia)

1. Bootblock stage: prepare to obtain lash access and look up the ROM stage to use
2. ROM stage: memory and early chipset init (a bit like PEI in EFI)
3. RAM stage: device enumeration and resource assignment, ACPI table creation, SMM handler (a bit like DXE stage in EFI)
4. Payload

The most difficult hardware that coreboot initalizes is the DRAM controllers and DRAM, RAM initialization is particularly difficult because before the RAM is initialied it cannot be used. So, to initialize DRAM controllers and DRAM, the initialization code may have only CPU's GPRs or Cache-as-RAM as temporary storage.
