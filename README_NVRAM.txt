THE FOLLOWING NOTES APPLY ONCE THE YOCTO LINUX IMAGE IS BUILT AND ROOTFS IS POPULATED:
======================================================================================
Use "murata-master" sub-folder for module-specific NVRAM file (NVRAM filename includes Murata module designation). 
Note that the FMAC driver loads a specific NVRAM filename when coming up: "cyfmac"+<CYW number>+<-sdio or -pcie>+".txt"
This means that for any Murata modules which share the same chipset, we can only have one NVRAM file present in the default folder: "/lib/firmware/cypress".
The following module NVRAM default files are included in this folder: 

Cypress Chipset		Default		Options		WLAN Interface    Devices Supported	  	             Notes
===============		=======		=======		==============    =====================   	==========================================================================================
CYW54591             1XA		N/A	             PCIe             802.11a/b/g/n/ac MIMO             Indoor/Station mode only
CYW54590             2BZ		N/A	             SDIO             802.11a/b/g/n/ac MIMO             Indoor/Station mode only
CYW43455             1MW		1LC, 1HK             SDIO             802.11a/b/g/n/ac		        1MW - Mass Market; 1LC, 1HK - Strategic customer engagement only. Indoor/Station mode only
CYW4373              2AE		N/A	             SDIO             802.11a/b/g/n/ac                  Indoor/Station mode only
CYW43012             1LV		N/A                  SDIO             802.11a/b/g/n/ac-friendly	        "802.11ac friendly"; MAX 20 MHz Bandwidth. Indoor/Station mode only
CYW43022             2GF		N/A                  SDIO             802.11a/b/g/n/ac-friendly	        "802.11ac friendly"; MAX 20 MHz Bandwidth. Indoor/Station mode only
CYW43430/CYW4343W    1DX		1LN                  SDIO             802.11b/g/n                       Indoor/Station mode only
CYW43439             1YN                N/A	             SDIO             802.11b/g/n                       Indoor/Station mode only
CYW43364             1FX                N/A                  SDIO             802.11b/g/n			Same WLAN core as 1DX. Indoor/Station mode only
CYW43340/CYW43341    1BW                N/A                  SDIO             802.11b/g/n			Legacy module; No longer supported.
CYW5557x             2EA/2EC                                 PCIe/SDIO        802.11a/b/g/n/ac                  Indoor/Station mode only


The following table lists out the "md5sum" for all the NVRAM files.
------------------------------------------------------------------------------
|   File Name                           |         md5sum                     |
|---------------------------------------|------------------------------------|
| cyfmac43455-sdio.1LC.txt              |   be2ac7d996004743f8da872891cdf94c |
| cyfmac43455-sdio.1MW.txt              |   03bf056ef1349b8791259f67e00c4bcc |
| cyfmac43012-sdio.1LV.txt              |   20c7984a20b6ffcd15a491775cfee847 |
| cyfmac43022-sdio.2GF.txt              |   5e5af0dd4c4f3907fd160cc947049814 |
| cyfmac43430-sdio.1FX.txt              |   ecee52eb58fd9921398ca5179e096949 |
| cyfmac43340-sdio.1BW.txt              |   7a1a7dbfd18f8f7a9b4086c920b819a1 |
| cyfmac43430-sdio.1DX.txt              |   ecee52eb58fd9921398ca5179e096949 |
| cyfmac54591-pcie.1XA.txt              |   edb53ed8f965ed562163414ed3edc8af |
| cyfmac43439-sdio.1YN.txt              |   e71588b34ab32409d52622355353f76c |
| cyfmac4373-sdio.2AE.txt               |   a42dd6b9c37c1e950c2aa840bd5f6c38 |
| cyfmac4373-sdio.2BC.txt               |   19b21a45ad1174545fb14992e3aa5dd8 |
| cyfmac55500-sdio.2FY.txt              |   028bcfc968e84ab069e77d1a8ddf4044 |
| cyfmac54591-sdio.2ant.2BZ.txt         |   f9255018ed4954b96b8d1eda8bab1a0f | 
| cyfmac54591-sdio.3ant.2BZ.txt         |   ee1c0ab8a0ffbc4d8aad5ae21d006b9c |
| cyfmac5557x-pcie_sdio.sant.2EA_2EC.txt|   43902ab9f0a8ee358e0ff2532c2ec299 |
| cyfmac5557x-pcie_sdio.dant.2EA_2EC.txt|   6ec92c9412809420171c964c095d5100 |
------------------------------------------------------------------------------

Note: (1) Same NVRAM file (cyfmac54591-sdio.txt) is used for 1XA and 2BZ. 2BZ is based out of IFX chipset 54590.
      (2) Same NVRAM files (cyfmac5557x-pcie_sdio.sant.2EA_2EC.txt/cyfmac5557x-pcie_sdio.dant.2EA_2EC.txt) are used for 2EA and 2EC. 2EC is based out of IFX chipset CYW55571.
