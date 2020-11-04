# SHS3321-NexT-Firmware
Firmware and Instructions to rollback an SHS3321 to accept a Dangerous Things NexT implant as an NFC tag.

Undertake at your own risk, this was tested on one (1) shs3321 that previously would not accept my NexT tag
(images and instructions comming)

## Requirements:
1. PICKit 3/4 (Other Options TBD)
      * [PICKit 3 Ebay US](https://www.ebay.com.au/itm/PICKit3-Microchip-Programmer-w-USB-cable-wires-Pic-Kit-3/331941067077?epid=668289631&hash=item4d493ab945:g:XGMAAOSwnHZYcAgs)
      * [PICKit 3 Ebay China](https://www.ebay.com.au/i/353165994935?chn=ps&mkevt=1&mkcid=28)
      * [PICKit 3 AliExpress](https://www.aliexpress.com/item/33005417188.html?src=google&albch=shopping&acnt=494-037-6276&isdl=y&slnk=&plac=&mtctp=&albbt=Google_7_shopping&aff_platform=google&aff_short_key=UneMJZVf&&albagn=888888&albcp=11491022111&albag=112291760596&trgt=743612850874&crea=en33005417188&netw=u&device=c&albpg=743612850874&albpd=en33005417188&gclid=CjwKCAiAnIT9BRAmEiwANaoE1QrcG4lsguq-KKKz5PyeOpsPfJ040YZ76Z78aur-ur9Pv2MumfmgGxoCGv0QAvD_BwE&gclsrc=aw.ds)



2. SHS3321 board GC41-00833A Rev.02
3. [Molex PicoBlade 15134 Series Number Wire to Board Cable Assembly 1 Row, 5 Way any length](https://au.rs-online.com/web/p/wire-to-board-cable-assemblies/1250738/?relevancy-data=7365617263685F636173636164655F6F726465723D31267365617263685F696E746572666163655F6E616D653D4931384E525353746F636B4E756D626572267365617263685F6C616E67756167655F757365643D656E267365617263685F6D617463685F6D6F64653D6D61746368616C6C267365617263685F7061747465726E5F6D6174636865643D5E2828282872737C5253295B205D3F293F285C647B337D5B5C2D5C735D3F5C647B332C347D5B705061415D3F29297C283235285C647B387D7C5C647B317D5C2D5C647B377D29292924267365617263685F7061747465726E5F6F726465723D31267365617263685F73745F6E6F726D616C697365643D59267365617263685F726573706F6E73655F616374696F6E3D267365617263685F747970653D52535F53544F434B5F4E554D424552267365617263685F77696C645F63617264696E675F6D6F64653D4E4F4E45267365617263685F6B6579776F72643D31323530373338267365617263685F6B6579776F72645F6170703D31323530373338267365617263685F636F6E6669673D3026&searchHistory=%7B%22enabled%22%3Atrue%7D)
4. [MPLAB IPE v5.45](https://www.microchip.com/mplab/mplab-x-ide)
## ICSP connector to PICkit3 Connections
ICSP is a 5 pin version of the PICkit3 connector,
match white arrow to white arrow

| PICkit3            | SHS3321 ICSP       |
|--------------------|--------------------|
| 1 (White Triangle) | 1 (White Triangle) |
| 2                  | 2                  |
| 3                  | 3                  |
| 4                  | 4                  |
| 5                  | 5                  |
| 6                  | NOT CONNECTED      |


## MPLAB IPE Settings
1. Enter advanced mode
    * Opperate -> Family: All Families
    * Opperate -> Device: PIC18f66k22
    * Opperate -> Tool: "PICkit3 S.No: XXXXXXXXXXX"
    * Power -> Power Target circuit from PICkit3: CHECKED
    * Power -> Voltage Level: 3.25
    * Memory -> Preserve EEPROM Memory: CHECKED
    * Memory -> Leave the rest default
    * Production -> Allow Export Hex: CHECKED
    * Production -> Allow Import Hex file: CHECKED
2. Opperate -> Tool -> Connect
## Backup Original Firmware
1. Opperate -> READ
2. File -> Export -> HEX
## Flash NeXT Firmware
1. Opperate -> Hex File -> Browse: "SHS3321 - PIC18F66K22 - NeXT.hex"
2. Opperate -> Program

### Expected "Output - IPE":

>2020-11-02 16:18:41 +1100 - Hex file loaded successfully.

>2020-11-02 16:18:48 +1100 - Programming...

>The following memory area(s) will be read:

>EEData memory

>2020-11-02 16:18:52 +1100 - Memory Updated: CRC32 checksum value is based on the loaded hex file.

>Device Erased...

>Programming...

>The following memory area(s) will be programmed:

>program memory: start address = 0x0, end address = 0x617f

>configuration memory

>EEData memory

>User Id Memory

>Programming/Verify complete

>2020-11-02 16:19:03 +1100 - Programming complete
