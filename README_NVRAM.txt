THE FOLLOWING NOTES APPLY ONCE THE YOCTO LINUX IMAGE IS BUILT AND ROOTFS IS POPULATED:
======================================================================================
Use "murata-master" sub-folder for module-specific NVRAM file (NVRAM filename includes Murata module designation). 
Note that the FMAC driver loads a specific NVRAM filename when coming up: "cyfmac"+<CYW number>+<-sdio or -pcie>+".txt"
This means that for any Murata modules which share the same chipset, we can only have one NVRAM file present in the default folder: "/lib/firmware/cypress".
The following module NVRAM default files are included in this folder: 

Cypress Chipset		Default		Options		WLAN Interface    Devices Supported	  	Notes
===============		=======		=======		==============    =====================   	===============================================================
CYW54591		1XA		N/A		PCIe              802.11a/b/g/n/ac MIMO
CYW4356			1CX		N/A		PCIe              802.11a/b/g/n/ac MIMO
CYW4354			1BB		N/A             SDIO              802.11a/b/g/n/ac MIMO		Strategic customer engagement only.
CYW43455		1MW		1LC, 1HK        SDIO              802.11a/b/g/n/ac		1MW - Mass Market; 1LC, 1HK - Strategic customer engagement only.
CYW4373                 2AE		N/A		SDIO              802.11a/b/g/n/ac
CYW43012		1LV		N/A             SDIO              802.11a/b/g/n/ac-friendly	"802.11ac friendly"; MAX 20 MHz Bandwidth.
CYW43430/CYW4343W	1DX		1LN             SDIO              802.11b/g/n
CYW43439                1YN		N/A		SDIO              802.11b/g/n
CYW43364                1FX             N/A             SDIO              802.11b/g/n			Same WLAN core as 1DX.
CYW4339			ZP		1CK             SDIO              802.11a/b/g/n/ac		Legacy module; No longer supported.
CYW43340/CYW43341	1BW		N/A             SDIO              802.11b/g/n			Legacy module; No longer supported.
CYW43362		SN8000		N/A	        SDIO              802.11b/g/n			Legacy module; No longer supported.


The following table lists out the "md5sum" for all the NVRAM files.
--------------------------------------------------------------------
|   File Name                 |         md5sum                     |
|-----------------------------|------------------------------------|
| cyfmac43430-sdio.1LN.txt    |   ecee52eb58fd9921398ca5179e096949 |
| cyfmac4339-sdio.1CK.txt     |   d1333ee70479132ce264d3f0f2ed310b |
| cyfmac43455-sdio.1LC.txt    |   be2ac7d996004743f8da872891cdf94c |
| cyfmac43455-sdio.1MW.txt    |   03bf056ef1349b8791259f67e00c4bcc |
| cyfmac43362-sdio.SN8000.txt |   3babb627c9b45d71ae3433a666863bf9 |
| cyfmac43012-sdio.1LV.txt    |   20c7984a20b6ffcd15a491775cfee847 |
| cyfmac4339-sdio.ZP.txt      |   073456f2106e2bb1f4564bdfcca2ca36 |
| cyfmac43430-sdio.1FX.txt    |   ecee52eb58fd9921398ca5179e096949 |
| cyfmac43455-sdio.1HK.txt    |   9b2a8bbfbf24a442d9013cd3a03ca4b1 |
| cyfmac4356-pcie.1CX.txt     |   b75378deafbd4c984236cad39266e5eb |
| cyfmac43340-sdio.1BW.txt    |   7a1a7dbfd18f8f7a9b4086c920b819a1 |
| cyfmac43430-sdio.1DX.txt    |   ecee52eb58fd9921398ca5179e096949 |
| cyfmac4354-sdio.1BB.txt     |   aa37432ae72808143a6be03399ca8244 |
| cyfmac54591-pcie.1XA.txt    |   edb53ed8f965ed562163414ed3edc8af |
| cyfmac43439-sdio.1YN.txt    |   f92125adc6425ce3f1c812e708580cb7 |
| cyfmac4373-sdio.2AE.txt     |   21945f2bcb30511ec0b8798e56898614 |
| cyfmac4373-sdio.2BC.txt     |   21945f2bcb30511ec0b8798e56898614 |
--------------------------------------------------------------------
