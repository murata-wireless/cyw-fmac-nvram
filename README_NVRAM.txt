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
CYW43012		1LV		N/A             SDIO              802.11a/b/g/n/ac-friendly	"802.11ac friendly"; MAX 20 MHz Bandwidth.
CYW43430/CYW4343W	1DX		1LN             SDIO              802.11b/g/n
CYW43364                1FX             N/A             SDIO              802.11b/g/n			Same WLAN core as 1DX.
CYW4339			ZP		1CK             SDIO              802.11a/b/g/n/ac		Legacy module; No longer supported.
CYW43340/CYW43341	1BW		N/A             SDIO              802.11b/g/n			Legacy module; No longer supported.
CYW43362		SN8000		N/A	        SDIO              802.11b/g/n			Legacy module; No longer supported.


The following table lists out the "md5sum" for all the NVRAM files.
--------------------------------------------------------------------
|   File Name                 |         md5sum                     |
|-----------------------------|------------------------------------|
| cyfmac43430-sdio.1LN.txt    |   680f28b5bb6cc75cdba3a8d96151924d |
| cyfmac4339-sdio.1CK.txt     |   4113e7f06ca64918cd01daffbbccb1b3 |
| cyfmac43455-sdio.1LC.txt    |   02998f5b252734af60a04a6a3d341119 |
| cyfmac43455-sdio.1MW.txt    |   01ca750418f4b4ad12635baf6b2644a7 |
| cyfmac43362-sdio.SN8000.txt |   a77318277df2a4dab8dab6b7caa2b275 |
| cyfmac43012-sdio.1LV.txt    |   84b035b040db08934dfd78cc600c3f7b |
| cyfmac4339-sdio.ZP.txt      |   1da222f231c065361b0a16e0bfc5fe3a |
| cyfmac43430-sdio.1FX.txt    |   680f28b5bb6cc75cdba3a8d96151924d |
| cyfmac43455-sdio.1HK.txt    |   a94d36a14e427b05aee1b90da1a38e16 |
| cyfmac4356-pcie.1CX.txt     |   d226c22a67b75ed08f7820e069b13ef3 |
| cyfmac43340-sdio.1BW.txt    |   796c44600f7ebfad31d1a1ddf43e8f35 |
| cyfmac43430-sdio.1DX.txt    |   680f28b5bb6cc75cdba3a8d96151924d |
| cyfmac4354-sdio.1BB.txt     |   4a129f22cb26f7d5c2298b84c8b480f9 |
| cyfmac54591-pcie.1XA.txt    |   0576859cf5bdf735cf353497b3037215 |
--------------------------------------------------------------------
