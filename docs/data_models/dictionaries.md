# Dictionaries

## Signal dictionaries

This chapter describes predefined constant values for use in the Signal environment

## Log level

The Signal log writing level 

| Level    | Write log messages level                    | When writes                                                       | Comment          |
|----------|---------------------------------------------|-------------------------------------------------------------------|------------------|
| NOTSET   | Do not write log at all                     | -                                                                 |                  |
| CRITICAL | `CRITICAL`                                  | Critical usually system errors                                    |                  |
| ERROR    | `CRITICAL` `ERROR`                          | The Signal cannot process user's request                          |                  |
| WARNING  | `CRITICAL` `ERROR` `WARNING`                | The Signal cannot process user's request as is, need some changes |                  |
| INFO     | `CRITICAL` `ERROR` `WARNING` `INFO`         | Regular Signal events                                             | Recommended mode |
| DEBUG    | `CRITICAL` `ERROR` `WARNING` `INFO` `DEBUG` | Write maximum information to log                                  | Writes raw dumps |

## Field Types

Fields predefined types

| Field Type             | Field should contain               |
|------------------------|------------------------------------|
| COUNTRY CODE           | Valid country code                 |
| CURRENCY CODE          | Valid currency code                |
| MERCHANT CATEGORY CODE | Valid Merchant Category Code (MCC) |
| DATE                   | Date or date and time              |
| OTHER                  | Other value, not from listing      |




## Validation Mode

Transaction data validation violation processing mode

| Mode     | Reaction                                                                                                         |
|----------|------------------------------------------------------------------------------------------------------------------|
| WARNING  | Set warning and process transaction                                                                              |
| ERROR    | Set error and stop transaction processing                                                                        |
| FLEXIBLE | Combined approach. Set error and stop on critical violation, set warning and process transaction on non-critical |


## Countries list
Countries list for data fields validation

| Name                                                 | Code N3  | Code A2 | Code A3 |
|------------------------------------------------------|----------|---------|---------|
| Afghanistan                                          | 004      | AF      | AFG     |
| Aland Islands                                        | 248      | AX      | ALA     |
| Albania                                              | 008      | AL      | ALB     |
| Algeria                                              | 012      | DZ      | DZA     |
| American Samoa                                       | 016      | AS      | ASM     |
| Andorra                                              | 020      | AD      | AND     |
| Angola                                               | 024      | AO      | AGO     |
| Anguilla                                             | 660      | AI      | AIA     |
| Antarctica                                           | 010      | AQ      | ATA     |
| Antigua and Barbuda                                  | 028      | AG      | ATG     |
| Argentina                                            | 032      | AR      | ARG     |
| Armenia                                              | 051      | AM      | ARM     |
| Aruba                                                | 533      | AW      | ABW     |
| Australia                                            | 036      | AU      | AUS     |
| Austria                                              | 040      | AT      | AUT     |
| Azerbaijan                                           | 031      | AZ      | AZE     |
| Bahamas                                              | 044      | BS      | BHS     |
| Bahrain                                              | 048      | BH      | BHR     |
| Bangladesh                                           | 050      | BD      | BGD     |
| Barbados                                             | 052      | BB      | BRB     |
| Belarus                                              | 112      | BY      | BLR     |
| Belgium                                              | 056      | BE      | BEL     |
| Belize                                               | 084      | BZ      | BLZ     |
| Benin                                                | 204      | BJ      | BEN     |
| Bermuda                                              | 060      | BM      | BMU     |
| Bhutan                                               | 064      | BT      | BTN     |
| Bolivia (Plurinational State of)                     | 068      | BO      | BOL     |
| Bonaire, Sint Eustatius and Saba                     | 535      | BQ      | BES     |
| Bosnia and Herzegovina                               | 070      | BA      | BIH     |
| Botswana                                             | 072      | BW      | BWA     |
| Bouvet Island                                        | 074      | BV      | BVT     |
| Brazil                                               | 076      | BR      | BRA     |
| British Indian Ocean Territory                       | 086      | IO      | IOT     |
| Brunei Darussalam                                    | 096      | BN      | BRN     |
| Bulgaria                                             | 100      | BG      | BGR     |
| Burkina Faso                                         | 854      | BF      | BFA     |
| Burundi                                              | 108      | BI      | BDI     |
| Cabo Verde                                           | 132      | CV      | CPV     |
| Cambodia                                             | 116      | KH      | KHM     |
| Cameroon                                             | 120      | CM      | CMR     |
| Canada                                               | 124      | CA      | CAN     |
| Cayman Islands                                       | 136      | KY      | CYM     |
| Central African Republic                             | 140      | CF      | CAF     |
| Chad                                                 | 148      | TD      | TCD     |
| Chile                                                | 152      | CL      | CHL     |
| China                                                | 156      | CN      | CHN     |
| Christmas Island                                     | 162      | CX      | CXR     |
| Cocos (Keeling) Islands                              | 166      | CC      | CCK     |
| Colombia                                             | 170      | CO      | COL     |
| Comoros                                              | 174      | KM      | COM     |
| Congo                                                | 178      | CG      | COG     |
| Congo, Democratic Republic of the                    | 180      | CD      | COD     |
| Cook Islands                                         | 184      | CK      | COK     |
| Costa Rica                                           | 188      | CR      | CRI     |
| Cote dIvoire                                         | 384      | CI      | CIV     |
| Croatia                                              | 191      | HR      | HRV     |
| Cuba                                                 | 192      | CU      | CUB     |
| Curacao                                              | 531      | CW      | CUW     |
| Cyprus                                               | 196      | CY      | CYP     |
| Czechia                                              | 203      | CZ      | CZE     |
| Denmark                                              | 208      | DK      | DNK     |
| Djibouti                                             | 262      | DJ      | DJI     |
| Dominica                                             | 212      | DM      | DMA     |
| Dominican Republic                                   | 214      | DO      | DOM     |
| Ecuador                                              | 218      | EC      | ECU     |
| Egypt                                                | 818      | EG      | EGY     |
| El Salvador                                          | 222      | SV      | SLV     |
| Equatorial Guinea                                    | 226      | GQ      | GNQ     |
| Eritrea                                              | 232      | ER      | ERI     |
| Estonia                                              | 233      | EE      | EST     |
| Eswatini                                             | 748      | SZ      | SWZ     |
| Ethiopia                                             | 231      | ET      | ETH     |
| Falkland Islands (Malvinas)                          | 238      | FK      | FLK     |
| Faroe Islands                                        | 234      | FO      | FRO     |
| Fiji                                                 | 242      | FJ      | FJI     |
| Finland                                              | 246      | FI      | FIN     |
| France                                               | 250      | FR      | FRA     |
| French Guiana                                        | 254      | GF      | GUF     |
| French Polynesia                                     | 258      | PF      | PYF     |
| French Southern Territories                          | 260      | TF      | ATF     |
| Gabon                                                | 266      | GA      | GAB     |
| Gambia                                               | 270      | GM      | GMB     |
| Georgia                                              | 268      | GE      | GEO     |
| Germany                                              | 276      | DE      | DEU     |
| Ghana                                                | 288      | GH      | GHA     |
| Gibraltar                                            | 292      | GI      | GIB     |
| Greece                                               | 300      | GR      | GRC     |
| Greenland                                            | 304      | GL      | GRL     |
| Grenada                                              | 308      | GD      | GRD     |
| Guadeloupe                                           | 312      | GP      | GLP     |
| Guam                                                 | 316      | GU      | GUM     |
| Guatemala                                            | 320      | GT      | GTM     |
| Guernsey                                             | 831      | GG      | GGY     |
| Guinea                                               | 324      | GN      | GIN     |
| Guinea-Bissau                                        | 624      | GW      | GNB     |
| Guyana                                               | 328      | GY      | GUY     |
| Haiti                                                | 332      | HT      | HTI     |
| Heard Island and McDonald Islands                    | 334      | HM      | HMD     |
| Holy See                                             | 336      | VA      | VAT     |
| Honduras                                             | 340      | HN      | HND     |
| Hong Kong                                            | 344      | HK      | HKG     |
| Hungary                                              | 348      | HU      | HUN     |
| Iceland                                              | 352      | IS      | ISL     |
| India                                                | 356      | IN      | IND     |
| Indonesia                                            | 360      | ID      | IDN     |
| Iran (Islamic Republic of)                           | 364      | IR      | IRN     |
| Iraq                                                 | 368      | IQ      | IRQ     |
| Ireland                                              | 372      | IE      | IRL     |
| Isle of Man                                          | 833      | IM      | IMN     |
| Israel                                               | 376      | IL      | ISR     |
| Italy                                                | 380      | IT      | ITA     |
| Jamaica                                              | 388      | JM      | JAM     |
| Japan                                                | 392      | JP      | JPN     |
| Jersey                                               | 832      | JE      | JEY     |
| Jordan                                               | 400      | JO      | JOR     |
| Kazakhstan                                           | 398      | KZ      | KAZ     |
| Kenya                                                | 404      | KE      | KEN     |
| Kiribati                                             | 296      | KI      | KIR     |
| Korea (Democratic Peoples Republic of)               | 408      | KP      | PRK     |
| Korea, Republic of                                   | 410      | KR      | KOR     |
| Kuwait                                               | 414      | KW      | KWT     |
| Kyrgyzstan                                           | 417      | KG      | KGZ     |
| Lao Peoples Democratic Republic                      | 418      | LA      | LAO     |
| Latvia                                               | 428      | LV      | LVA     |
| Lebanon                                              | 422      | LB      | LBN     |
| Lesotho                                              | 426      | LS      | LSO     |
| Liberia                                              | 430      | LR      | LBR     |
| Libya                                                | 434      | LY      | LBY     |
| Liechtenstein                                        | 438      | LI      | LIE     |
| Lithuania                                            | 440      | LT      | LTU     |
| Luxembourg                                           | 442      | LU      | LUX     |
| Macao                                                | 446      | MO      | MAC     |
| Madagascar                                           | 450      | MG      | MDG     |
| Malawi                                               | 454      | MW      | MWI     |
| Malaysia                                             | 458      | MY      | MYS     |
| Maldives                                             | 462      | MV      | MDV     |
| Mali                                                 | 466      | ML      | MLI     |
| Malta                                                | 470      | MT      | MLT     |
| Marshall Islands                                     | 584      | MH      | MHL     |
| Martinique                                           | 474      | MQ      | MTQ     |
| Mauritania                                           | 478      | MR      | MRT     |
| Mauritius                                            | 480      | MU      | MUS     |
| Mayotte                                              | 175      | YT      | MYT     |
| Mexico                                               | 484      | MX      | MEX     |
| Micronesia (Federated States of)                     | 583      | FM      | FSM     |
| Moldova, Republic of                                 | 498      | MD      | MDA     |
| Monaco                                               | 492      | MC      | MCO     |
| Mongolia                                             | 496      | MN      | MNG     |
| Montenegro                                           | 499      | ME      | MNE     |
| Montserrat                                           | 500      | MS      | MSR     |
| Morocco                                              | 504      | MA      | MAR     |
| Mozambique                                           | 508      | MZ      | MOZ     |
| Myanmar                                              | 104      | MM      | MMR     |
| Namibia                                              | 516      | NA      | NAM     |
| Nauru                                                | 520      | NR      | NRU     |
| Nepal                                                | 524      | NP      | NPL     |
| Netherlands                                          | 528      | NL      | NLD     |
| New Caledonia                                        | 540      | NC      | NCL     |
| New Zealand                                          | 554      | NZ      | NZL     |
| Nicaragua                                            | 558      | NI      | NIC     |
| Niger                                                | 562      | NE      | NER     |
| Nigeria                                              | 566      | NG      | NGA     |
| Niue                                                 | 570      | NU      | NIU     |
| Norfolk Island                                       | 574      | NF      | NFK     |
| North Macedonia                                      | 807      | MK      | MKD     |
| Northern Mariana Islands                             | 580      | MP      | MNP     |
| Norway                                               | 578      | NO      | NOR     |
| Oman                                                 | 512      | OM      | OMN     |
| Pakistan                                             | 586      | PK      | PAK     |
| Palau                                                | 585      | PW      | PLW     |
| Palestine, State of                                  | 275      | PS      | PSE     |
| Panama                                               | 591      | PA      | PAN     |
| Papua New Guinea                                     | 598      | PG      | PNG     |
| Paraguay                                             | 600      | PY      | PRY     |
| Peru                                                 | 604      | PE      | PER     |
| Philippines                                          | 608      | PH      | PHL     |
| Pitcairn                                             | 612      | PN      | PCN     |
| Poland                                               | 616      | PL      | POL     |
| Portugal                                             | 620      | PT      | PRT     |
| Puerto Rico                                          | 630      | PR      | PRI     |
| Qatar                                                | 634      | QA      | QAT     |
| Reunion                                              | 638      | RE      | REU     |
| Romania                                              | 642      | RO      | ROU     |
| Russian Federation                                   | 643      | RU      | RUS     |
| Rwanda                                               | 646      | RW      | RWA     |
| Saint Barthelemy                                     | 652      | BL      | BLM     |
| Saint Helena, Ascension and Tristan da Cunha         | 654      | SH      | SHN     |
| Saint Kitts and Nevis                                | 659      | KN      | KNA     |
| Saint Lucia                                          | 662      | LC      | LCA     |
| Saint Martin (French part)                           | 663      | MF      | MAF     |
| Saint Pierre and Miquelon                            | 666      | PM      | SPM     |
| Saint Vincent and the Grenadines                     | 670      | VC      | VCT     |
| Samoa                                                | 882      | WS      | WSM     |
| San Marino                                           | 674      | SM      | SMR     |
| Sao Tome and Principe                                | 678      | ST      | STP     |
| Saudi Arabia                                         | 682      | SA      | SAU     |
| Senegal                                              | 686      | SN      | SEN     |
| Serbia                                               | 688      | RS      | SRB     |
| Seychelles                                           | 690      | SC      | SYC     |
| Sierra Leone                                         | 694      | SL      | SLE     |
| Singapore                                            | 702      | SG      | SGP     |
| Sint Maarten (Dutch part)                            | 534      | SX      | SXM     |
| Slovakia                                             | 703      | SK      | SVK     |
| Slovenia                                             | 705      | SI      | SVN     |
| Solomon Islands                                      | 090      | SB      | SLB     |
| Somalia                                              | 706      | SO      | SOM     |
| South Africa                                         | 710      | ZA      | ZAF     |
| South Georgia and the South Sandwich Islands         | 239      | GS      | SGS     |
| South Sudan                                          | 728      | SS      | SSD     |
| Spain                                                | 724      | ES      | ESP     |
| Sri Lanka                                            | 144      | LK      | LKA     |
| Sudan                                                | 729      | SD      | SDN     |
| Suriname                                             | 740      | SR      | SUR     |
| Svalbard and Jan Mayen                               | 744      | SJ      | SJM     |
| Sweden                                               | 752      | SE      | SWE     |
| Switzerland                                          | 756      | CH      | CHE     |
| Syrian Arab Republic                                 | 760      | SY      | SYR     |
| Taiwan, Province of China                            | 158      | TW      | TWN     |
| Tajikistan                                           | 762      | TJ      | TJK     |
| Tanzania, United Republic of                         | 834      | TZ      | TZA     |
| Thailand                                             | 764      | TH      | THA     |
| Timor-Leste                                          | 626      | TL      | TLS     |
| Togo                                                 | 768      | TG      | TGO     |
| Tokelau                                              | 772      | TK      | TKL     |
| Tonga                                                | 776      | TO      | TON     |
| Trinidad and Tobago                                  | 780      | TT      | TTO     |
| Tunisia                                              | 788      | TN      | TUN     |
| Turkey                                               | 792      | TR      | TUR     |
| Turkmenistan                                         | 795      | TM      | TKM     |
| Turks and Caicos Islands                             | 796      | TC      | TCA     |
| Tuvalu                                               | 798      | TV      | TUV     |
| Uganda                                               | 800      | UG      | UGA     |
| Ukraine                                              | 804      | UA      | UKR     |
| United Arab Emirates                                 | 784      | AE      | ARE     |
| United Kingdom of Great Britain and Northern Ireland | 826      | GB      | GBR     |
| United States of America                             | 840      | US      | USA     |
| United States Minor Outlying Islands                 | 581      | UM      | UMI     |
| Uruguay                                              | 858      | UY      | URY     |
| Uzbekistan                                           | 860      | UZ      | UZB     |
| Vanuatu                                              | 548      | VU      | VUT     |
| Venezuela (Bolivarian Republic of)                   | 862      | VE      | VEN     |
| Viet Nam                                             | 704      | VN      | VNM     |
| Virgin Islands (British)                             | 092      | VG      | VGB     |
| Virgin Islands (U.S.)                                | 850      | VI      | VIR     |
| Wallis and Futuna                                    | 876      | WF      | WLF     |
| Western Sahara                                       | 732      | EH      | ESH     |
| Yemen                                                | 887      | YE      | YEM     |
| Zambia                                               | 894      | ZM      | ZMB     |
| Zimbabwe                                             | 716      | ZW      | ZWE     |



## Currencies list

Currencies list for data fields validation

| Code A3 | Exponent | Name                                                       | Code N3 |
|---------|----------|------------------------------------------------------------|---------|
| AED     | 2        | United Arab Emirates dirham                                | 784     |
| AFN     | 2        | Afghan afghani                                             | 971     |
| ALL     | 2        | Albanian lek                                               | 008     |
| AMD     | 2        | Armenian dram                                              | 051     |
| ANG     | 2        | Netherlands Antillean guilder                              | 532     |
| AOA     | 2        | Angolan kwanza                                             | 973     |
| ARS     | 2        | Argentine peso                                             | 032     |
| AUD     | 2        | Australian dollar                                          | 036     |
| AWG     | 2        | Aruban florin                                              | 533     |
| AZN     | 2        | Azerbaijani manat                                          | 944     |
| BAM     | 2        | Bosnia and Herzegovina convertible mark                    | 977     |
| BBD     | 2        | Barbados dollar                                            | 052     |
| BDT     | 2        | Bangladeshi taka                                           | 050     |
| BGN     | 2        | Bulgarian lev                                              | 975     |
| BHD     | 3        | Bahraini dinar                                             | 048     |
| BIF     | 0        | Burundian franc                                            | 108     |
| BMD     | 2        | Bermudian dollar (customarily known as Bermuda dollar)     | 060     |
| BND     | 2        | Brunei dollar                                              | 096     |
| BOB     | 2        | Boliviano                                                  | 068     |
| BOV     | 2        | Bolivian Mvdol                                             | 984     |
| BRL     | 2        | Brazilian real                                             | 986     |
| BSD     | 2        | Bahamian dollar                                            | 044     |
| BTN     | 2        | Bhutanese ngultrum                                         | 064     |
| BWP     | 2        | Botswana pula                                              | 072     |
| BYR     | 0        | Belarusian ruble                                           | 974     |
| BZD     | 2        | Belize dollar                                              | 084     |
| CAD     | 2        | Canadian dollar                                            | 124     |
| CDF     | 2        | Congolese franc                                            | 976     |
| CHE     | 2        | WIR Euro (complementary currency)                          | 947     |
| CHF     | 2        | Swiss franc                                                | 756     |
| CHW     | 2        | WIR Franc (complementary currency)                         | 948     |
| CLF     | 0        | Unidad de Fomento                                          | 990     |
| CLP     | 0        | Chilean peso                                               | 152     |
| CNY     | 2        | Chinese yuan                                               | 156     |
| COP     | 2        | Colombian peso                                             | 170     |
| COU     | 2        | Unidad de Valor Real                                       | 970     |
| CRC     | 2        | Costa Rican colon                                          | 188     |
| CUC     | 2        | Cuban convertible peso                                     | 931     |
| CUP     | 2        | Cuban peso                                                 | 192     |
| CVE     | 0        | Cape Verde escudo                                          | 132     |
| CZK     | 2        | Czech koruna                                               | 203     |
| DJF     | 0        | Djiboutian franc                                           | 262     |
| DKK     | 2        | Danish krone                                               | 208     |
| DOP     | 2        | Dominican peso                                             | 214     |
| DZD     | 2        | Algerian dinar                                             | 012     |
| EGP     | 2        | Egyptian pound                                             | 818     |
| ERN     | 2        | Eritrean nakfa                                             | 232     |
| ETB     | 2        | Ethiopian birr                                             | 230     |
| EUR     | 2        | Euro                                                       | 978     |
| FJD     | 2        | Fiji dollar                                                | 242     |
| FKP     | 2        | Falkland Islands pound                                     | 238     |
| GBP     | 2        | Pound sterling                                             | 826     |
| GEL     | 2        | Georgian lari                                              | 981     |
| GHS     | 2        | Ghanaian cedi                                              | 936     |
| GIP     | 2        | Gibraltar pound                                            | 292     |
| GMD     | 2        | Gambian dalasi                                             | 270     |
| GNF     | 0        | Guinean franc                                              | 324     |
| GTQ     | 2        | Guatemalan quetzal                                         | 320     |
| GYD     | 2        | Guyanese dollar                                            | 328     |
| HKD     | 2        | Hong Kong dollar                                           | 344     |
| HNL     | 2        | Honduran lempira                                           | 340     |
| HRK     | 2        | Croatian kuna                                              | 191     |
| HTG     | 2        | Haitian gourde                                             | 332     |
| HUF     | 2        | Hungarian forint                                           | 348     |
| IDR     | 2        | Indonesian rupiah                                          | 360     |
| ILS     | 2        | Israeli new shekel                                         | 376     |
| INR     | 2        | Indian rupee                                               | 356     |
| IQD     | 3        | Iraqi dinar                                                | 368     |
| IRR     | 0        | Iranian rial                                               | 364     |
| ISK     | 0        | Icelandic króna                                            | 352     |
| JMD     | 2        | Jamaican dollar                                            | 388     |
| JOD     | 3        | Jordanian dinar                                            | 400     |
| JPY     | 0        | Japanese yen                                               | 392     |
| KES     | 2        | Kenyan shilling                                            | 404     |
| KGS     | 2        | Kyrgyzstani som                                            | 417     |
| KHR     | 2        | Cambodian riel                                             | 116     |
| KMF     | 0        | Comoro franc                                               | 174     |
| KPW     | 0        | North Korean won                                           | 408     |
| KRW     | 0        | South Korean won                                           | 410     |
| KWD     | 3        | Kuwaiti dinar                                              | 414     |
| KYD     | 2        | Cayman Islands dollar                                      | 136     |
| KZT     | 2        | Kazakhstani tenge                                          | 398     |
| LAK     | 0        | Lao kip                                                    | 418     |
| LBP     | 0        | Lebanese pound                                             | 422     |
| LKR     | 2        | Sri Lankan rupee                                           | 144     |
| LRD     | 2        | Liberian dollar                                            | 430     |
| LSL     | 2        | Lesotho loti                                               | 426     |
| LTL     | 2        | Lithuanian litas                                           | 440     |
| LVL     | 2        | Latvian lats                                               | 428     |
| LYD     | 3        | Libyan dinar                                               | 434     |
| MAD     | 2        | Moroccan dirham                                            | 504     |
| MDL     | 2        | Moldovan leu                                               | 498     |
| MGA     | 0        | Malagasy ariary                                            | 969     |
| MKD     | 0        | Macedonian denar                                           | 807     |
| MMK     | 0        | Myanma kyat                                                | 104     |
| MNT     | 2        | Mongolian tugrik                                           | 496     |
| MOP     | 2        | Macanese pataca                                            | 446     |
| MRO     | 0        | Mauritanian ouguiya                                        | 478     |
| MUR     | 2        | Mauritian rupee                                            | 480     |
| MVR     | 2        | Maldivian rufiyaa                                          | 462     |
| MWK     | 2        | Malawian kwacha                                            | 454     |
| MXN     | 2        | Mexican peso                                               | 484     |
| MXV     | 2        | Mexican Unidad de Inversion (UDI)                          | 979     |
| MYR     | 2        | Malaysian ringgit                                          | 458     |
| MZN     | 2        | Mozambican metical                                         | 943     |
| NAD     | 2        | Namibian dollar                                            | 516     |
| NGN     | 2        | Nigerian naira                                             | 566     |
| NIO     | 2        | Nicaraguan córdoba                                         | 558     |
| NOK     | 2        | Norwegian krone                                            | 578     |
| NPR     | 2        | Nepalese rupee                                             | 524     |
| NZD     | 2        | New Zealand dollar                                         | 554     |
| OMR     | 3        | Omani rial                                                 | 512     |
| PAB     | 2        | Panamanian balboa                                          | 590     |
| PEN     | 2        | Peruvian nuevo sol                                         | 604     |
| PGK     | 2        | Papua New Guinean kina                                     | 598     |
| PHP     | 2        | Philippine peso                                            | 608     |
| PKR     | 2        | Pakistani rupee                                            | 586     |
| PLN     | 2        | Polish złoty                                               | 985     |
| PYG     | 0        | Paraguayan guaraní                                         | 600     |
| QAR     | 2        | Qatari riyal                                               | 634     |
| RON     | 2        | Romanian new leu                                           | 946     |
| RSD     | 2        | Serbian dinar                                              | 941     |
| RUB     | 2        | Russian rouble                                             | 643     |
| RWF     | 0        | Rwandan franc                                              | 646     |
| SAR     | 2        | Saudi riyal                                                | 682     |
| SBD     | 2        | Solomon Islands dollar                                     | 090     |
| SCR     | 2        | Seychelles rupee                                           | 690     |
| SDG     | 2        | Sudanese pound                                             | 938     |
| SEK     | 2        | Swedish krona/kronor                                       | 752     |
| SGD     | 2        | Singapore dollar                                           | 702     |
| SHP     | 2        | Saint Helena pound                                         | 654     |
| SLL     | 0        | Sierra Leonean leone                                       | 694     |
| SOS     | 2        | Somali shilling                                            | 706     |
| SRD     | 2        | Surinamese dollar                                          | 968     |
| SSP     | 2        | South Sudanese pound                                       | 728     |
| STD     | 0        | São Tomé and Príncipe dobra                                | 678     |
| SYP     | 2        | Syrian pound                                               | 760     |
| SZL     | 2        | Swazi lilangeni                                            | 748     |
| THB     | 2        | Thai baht                                                  | 764     |
| TJS     | 2        | Tajikistani somoni                                         | 972     |
| TMT     | 2        | Turkmenistani manat                                        | 934     |
| TND     | 3        | Tunisian dinar                                             | 788     |
| TOP     | 2        | Tongan paʻanga                                             | 776     |
| TRY     | 2        | Turkish lira                                               | 949     |
| TTD     | 2        | Trinidad and Tobago dollar                                 | 780     |
| TWD     | 2        | New Taiwan dollar                                          | 901     |
| TZS     | 2        | Tanzanian shilling                                         | 834     |
| UAH     | 2        | Ukrainian hryvnia                                          | 980     |
| UGX     | 2        | Ugandan shilling                                           | 800     |
| USD     | 2        | United States dollar                                       | 840     |
| USN     | 2        | United States dollar (next day)                            | 997     |
| USS     | 2        | United States dollar                                       | 998     |
| UYI     | 0        | Uruguay Peso en Unidades Indexadas (URUIURUI)              | 940     |
| UYU     | 2        | Uruguayan peso                                             | 858     |
| UZS     | 2        | Uzbekistan som                                             | 860     |
| VEF     | 2        | Venezuelan bolívar fuerte                                  | 937     |
| VND     | 0        | Vietnamese dong                                            | 704     |
| VUV     | 0        | Vanuatu vatu                                               | 548     |
| WST     | 2        | Samoan tala                                                | 882     |
| XAF     | 0        | CFA franc BEAC                                             | 950     |
| XAG     | 0        | Silver (one troy ounce)                                    | 961     |
| XAU     | 0        | Gold (one troy ounce)                                      | 959     |
| XBA     | 0        | European Composite Unit (EURCO) (bond market unit)         | 955     |
| XBB     | 0        | European Monetary Unit (E.M.U.-6) (bond market unit)       | 956     |
| XBC     | 0        | European Unit of Account 9 (E.U.A.-9) (bond market unit)   | 957     |
| XBD     | 0        | European Unit of Account 17 (E.U.A.-17) (bond market unit) | 958     |
| XCD     | 2        | East Caribbean dollar                                      | 951     |
| XDR     | 0        | Special drawing rights                                     | 960     |
| XOF     | 0        | CFA franc BCEAO                                            | 952     |
| XPD     | 0        | Palladium (one troy ounce)                                 | 964     |
| XPF     | 0        | CFP franc                                                  | 953     |
| XPT     | 0        | Platinum (one troy ounce)                                  | 962     |
| XTS     | 0        | code_a3 reserved for testing purposes                      | 963     |
| XXX     | 0        | No currency                                                | 999     |
| YER     | 2        | Yemeni rial                                                | 886     |
| ZAR     | 2        | South African rand                                         | 710     |
| ZMW     | 2        | Zambian kwacha                                             | 967     |
