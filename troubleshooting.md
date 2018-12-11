# Troubleshooting
Troubleshooting problems in DSX Desktop.

## Compatibility
DSX Desktop works on all platforms (MacOS, Windows 7, Windows 10, and Linux), but certain platforms have more issues than others.
* MacOS and Linux have very few (if any) issues, the majority of them are Windows.
* Windows 10 Enterprise, Pro, and Education has [Hyper-V](https://docs.microsoft.com/en-us/virtualization/hyper-v-on-windows/quick-start/enable-hyper-v), which enables Docker to run natively, which is less error-prone.
* Windows 7 and Windows 10 Home runs Docker inside a VirtualBox VM, which is very error-prone.
