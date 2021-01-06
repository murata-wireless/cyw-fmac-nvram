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
| cyfmac43430-sdio.1LN.txt    |   3fece53a5dcb6ca66ba63fcae0510989 |
| cyfmac4339-sdio.1CK.txt     |   bc0c8bb08a34efdeee85c26eae001277 |
| cyfmac43455-sdio.1LC.txt    |   4b1d3d64dae4180c15a1df8d85c9cf8a |
| cyfmac43455-sdio.1MW.txt    |   f5f5bd320388d3180ae8d436fcd063a3 |
| cyfmac43362-sdio.SN8000.txt |   675f8049f4f064a5859629ee1fc1d85d |
| cyfmac43012-sdio.1LV.txt    |   e14efe7bbe52af1719deba7afe5a4281 |
| cyfmac4339-sdio.ZP.txt      |   7df2faa6c8b981c4bc4a54f613dad091 |
| cyfmac43430-sdio.1FX.txt    |   3fece53a5dcb6ca66ba63fcae0510989 |
| cyfmac43455-sdio.1HK.txt    |   e855115a09e07448c17b0909a8e54a30 |
| cyfmac4356-pcie.1CX.txt     |   f08591b6318ee7f3f36644c2bb5483b3 |
| cyfmac43340-sdio.1BW.txt    |   410b34f865d7b478bab23ec6858ec7f6 |
| cyfmac43430-sdio.1DX.txt    |   3fece53a5dcb6ca66ba63fcae0510989 |
| cyfmac4354-sdio.1BB.txt     |   c7a5bc11eeaf3cfb4c12c97c668c2499 |
| cyfmac54591-pcie.1XA.txt    |   1bd2c7fcbff3e2082c848f29cb3e60c5 |
--------------------------------------------------------------------
