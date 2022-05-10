---
uid: aeaa732d-3cc8-4673-9817-15f0cc125ba6
---

# Protektor

If you need to deploy a vvvv project and want to protect your source code (intellectual property) and to make sure that it is only running a certain number of copies or for a certain period of time you can use a vvvv dongle. 

![](~/img/dongle_0.png "")

For an additional fee to the basic <a href="https://shop.vvvv.org" class="extURL" target="_blank">licensing</a> costs you can buy a dongle (for each license). With a dongle you get access to the Protektor tool that allows you to protect your work from being run without your permission. While the files of your project can still be copied freely vvvv will only run them if a dongle that you prepared is present. And even with the dongle present vvvv will not display your patches but only renderers.

---

Protection works for x86 and x64 builds of vvvv and also supports [boygrouping](xref:9d029794-1266-4e60-961f-33e6f95af7e6) setups in which every client and server needs a dongle.

The following types of files are being encrypted:

* v4p
* fx (dx9 only)

By design the system always protects a whole project and can then only load protected files. Running a project with a mix of protected and unprotected source files is not possible.

In a patch you can use <span class="node">Dongle (VVVV)</span> to check for the presence of the dongle periodically and take according action if the dongle is missing.

For pricing and ordering please see <a href="https://shop.vvvv.org" class="extURL" target="_blank">Licensing</a>.