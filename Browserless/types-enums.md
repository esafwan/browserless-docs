# Browserless Enums Documentation



---

## Enum: AttributeMode
Source: https://docs.browserless.io/bql-schema/types/enums/attribute-mode

* * Types* Enums* AttributeMode

Open in ChatGPT

On this page

# AttributeMode

Controls how the attributes field is interpreted in cleaning operations

```
enum AttributeMode {  
  ALLOW  
  DENY  
}
```

### Values[​](#values "Direct link to Values")

#### [`AttributeMode.ALLOW`](#)[​](#attributemodeallow "Direct link to attributemodeallow")

The attributes field specifies which attributes to keep (preserve only these)

#### [`AttributeMode.DENY`](#)[​](#attributemodedeny "Direct link to attributemodedeny")

The attributes field specifies which attributes to remove (remove only these)

### Member Of[​](#member-of "Direct link to Member Of")

[`CleanInput`](/bql-schema/types/inputs/clean-input) input

---

## Enum: CaptchaTypes
Source: https://docs.browserless.io/bql-schema/types/enums/captcha-types

* * Types* Enums* CaptchaTypes

Open in ChatGPT

On this page

# CaptchaTypes

The different types of captchas that can be solved

```
enum CaptchaTypes {  
  recaptcha  
  recaptchaV3  
  geetest  
  normal  
  friendlyCaptcha  
  capy  
  textCaptcha  
  amazonWaf  
}
```

### Values[​](#values "Direct link to Values")

#### [`CaptchaTypes.recaptcha`](#)[​](#captchatypesrecaptcha "Direct link to captchatypesrecaptcha")

reCAPTCHA captcha type

#### [`CaptchaTypes.recaptchaV3`](#)[​](#captchatypesrecaptchav3 "Direct link to captchatypesrecaptchav3")

reCAPTCHA v3 captcha type

#### [`CaptchaTypes.geetest`](#)[​](#captchatypesgeetest "Direct link to captchatypesgeetest")

GeeTest captcha type

#### [`CaptchaTypes.normal`](#)[​](#captchatypesnormal "Direct link to captchatypesnormal")

Normal captcha type

#### [`CaptchaTypes.friendlyCaptcha`](#)[​](#captchatypesfriendlycaptcha "Direct link to captchatypesfriendlycaptcha")

friendlyCaptcha captcha type

#### [`CaptchaTypes.capy`](#)[​](#captchatypescapy "Direct link to captchatypescapy")

Capy captcha type

#### [`CaptchaTypes.textCaptcha`](#)[​](#captchatypestextcaptcha "Direct link to captchatypestextcaptcha")

textCaptcha captcha type

#### [`CaptchaTypes.amazonWaf`](#)[​](#captchatypesamazonwaf "Direct link to captchatypesamazonwaf")

amazonWaf captcha type

### Member Of[​](#member-of "Direct link to Member Of")

[`solve`](/bql-schema/operations/mutations/solve) mutation

---

## Enum: CookieSameSite
Source: https://docs.browserless.io/bql-schema/types/enums/cookie-same-site

* * Types* Enums* CookieSameSite

Open in ChatGPT

On this page

# CookieSameSite

The values a cookie's SameSite attribute can hold

```
enum CookieSameSite {  
  Strict  
  Lax  
  None  
}
```

### Values[​](#values "Direct link to Values")

#### [`CookieSameSite.Strict`](#)[​](#cookiesamesitestrict "Direct link to cookiesamesitestrict")

Cookies are only sent in a first-party context and not sent along with requests initiated by third party websites

#### [`CookieSameSite.Lax`](#)[​](#cookiesamesitelax "Direct link to cookiesamesitelax")

Cookies are withheld on cross-site sub-requests, such as calls to load images or frames, but are sent when a user navigates to the URL from an external site

#### [`CookieSameSite.None`](#)[​](#cookiesamesitenone "Direct link to cookiesamesitenone")

Cookies are sent in all contexts, in responses to both first-party and cross-origin requests

### Member Of[​](#member-of "Direct link to Member Of")

[`CookieInput`](/bql-schema/types/inputs/cookie-input) input ● [`StandardCookie`](/bql-schema/types/objects/standard-cookie) object

---

## Enum: CountryType
Source: https://docs.browserless.io/bql-schema/types/enums/country-type

* * Types* Enums* CountryType

Open in ChatGPT

On this page

# CountryType

The two-letter ISO code for the specified country

```
enum CountryType {  
  AD  
  AE  
  AF  
  AG  
  AL  
  AM  
  AO  
  AR  
  AT  
  AU  
  AW  
  AX  
  AZ  
  BA  
  BB  
  BD  
  BE  
  BF  
  BG  
  BH  
  BI  
  BJ  
  BM  
  BN  
  BO  
  BQ  
  BR  
  BS  
  BT  
  BW  
  BY  
  BZ  
  CA  
  CD  
  CG  
  CH  
  CI  
  CL  
  CM  
  CN  
  CO  
  CR  
  CU  
  CV  
  CW  
  CY  
  CZ  
  DE  
  DJ  
  DK  
  DM  
  DO  
  DZ  
  EC  
  EE  
  EG  
  ES  
  ET  
  FI  
  FJ  
  FO  
  FR  
  GA  
  GB  
  GD  
  GE  
  GF  
  GG  
  GH  
  GI  
  GM  
  GN  
  GP  
  GR  
  GT  
  GU  
  GY  
  HK  
  HN  
  HR  
  HT  
  HU  
  ID  
  IE  
  IL  
  IM  
  IN  
  IQ  
  IR  
  IS  
  IT  
  JE  
  JM  
  JO  
  JP  
  KE  
  KG  
  KH  
  KN  
  KR  
  KW  
  KY  
  KZ  
  LA  
  LB  
  LC  
  LI  
  LK  
  LR  
  LS  
  LT  
  LU  
  LV  
  LY  
  MA  
  MC  
  MD  
  ME  
  MG  
  MK  
  ML  
  MM  
  MN  
  MO  
  MQ  
  MR  
  MS  
  MT  
  MU  
  MV  
  MW  
  MX  
  MY  
  MZ  
  NA  
  NC  
  NG  
  NI  
  NL  
  NO  
  NP  
  NZ  
  OM  
  PA  
  PE  
  PF  
  PG  
  PH  
  PK  
  PL  
  PR  
  PS  
  PT  
  PY  
  QA  
  RE  
  RO  
  RS  
  RU  
  RW  
  SC  
  SE  
  SG  
  SI  
  SK  
  SL  
  SM  
  SN  
  SO  
  SR  
  SS  
  ST  
  SV  
  SX  
  SY  
  SZ  
  TC  
  TG  
  TH  
  TJ  
  TN  
  TR  
  TT  
  TW  
  TZ  
  UA  
  UG  
  US  
  UY  
  UZ  
  VC  
  VE  
  VG  
  VI  
  VN  
  WS  
  YT  
  ZA  
  ZM  
  ZW  
}
```

### Values[​](#values "Direct link to Values")

#### [`CountryType.AD`](#)[​](#countrytypead "Direct link to countrytypead")

Andorra

#### [`CountryType.AE`](#)[​](#countrytypeae "Direct link to countrytypeae")

United Arab Emirates

#### [`CountryType.AF`](#)[​](#countrytypeaf "Direct link to countrytypeaf")

Afghanistan

#### [`CountryType.AG`](#)[​](#countrytypeag "Direct link to countrytypeag")

Antigua and Barbuda

#### [`CountryType.AL`](#)[​](#countrytypeal "Direct link to countrytypeal")

Albania

#### [`CountryType.AM`](#)[​](#countrytypeam "Direct link to countrytypeam")

Armenia

#### [`CountryType.AO`](#)[​](#countrytypeao "Direct link to countrytypeao")

Angola

#### [`CountryType.AR`](#)[​](#countrytypear "Direct link to countrytypear")

Argentina

#### [`CountryType.AT`](#)[​](#countrytypeat "Direct link to countrytypeat")

Austria

#### [`CountryType.AU`](#)[​](#countrytypeau "Direct link to countrytypeau")

Australia

#### [`CountryType.AW`](#)[​](#countrytypeaw "Direct link to countrytypeaw")

Aruba

#### [`CountryType.AX`](#)[​](#countrytypeax "Direct link to countrytypeax")

Åland Islands

#### [`CountryType.AZ`](#)[​](#countrytypeaz "Direct link to countrytypeaz")

Azerbaijan

#### [`CountryType.BA`](#)[​](#countrytypeba "Direct link to countrytypeba")

Bosnia and Herzegovina

#### [`CountryType.BB`](#)[​](#countrytypebb "Direct link to countrytypebb")

Barbados

#### [`CountryType.BD`](#)[​](#countrytypebd "Direct link to countrytypebd")

Bangladesh

#### [`CountryType.BE`](#)[​](#countrytypebe "Direct link to countrytypebe")

Belgium

#### [`CountryType.BF`](#)[​](#countrytypebf "Direct link to countrytypebf")

Burkina Faso

#### [`CountryType.BG`](#)[​](#countrytypebg "Direct link to countrytypebg")

Bulgaria

#### [`CountryType.BH`](#)[​](#countrytypebh "Direct link to countrytypebh")

Bahrain

#### [`CountryType.BI`](#)[​](#countrytypebi "Direct link to countrytypebi")

Burundi

#### [`CountryType.BJ`](#)[​](#countrytypebj "Direct link to countrytypebj")

Benin

#### [`CountryType.BM`](#)[​](#countrytypebm "Direct link to countrytypebm")

Bermuda

#### [`CountryType.BN`](#)[​](#countrytypebn "Direct link to countrytypebn")

Brunei Darussalam

#### [`CountryType.BO`](#)[​](#countrytypebo "Direct link to countrytypebo")

Plurinational State of Bolivia

#### [`CountryType.BQ`](#)[​](#countrytypebq "Direct link to countrytypebq")

Sint Eustatius and Saba Bonaire

#### [`CountryType.BR`](#)[​](#countrytypebr "Direct link to countrytypebr")

Brazil

#### [`CountryType.BS`](#)[​](#countrytypebs "Direct link to countrytypebs")

Bahamas

#### [`CountryType.BT`](#)[​](#countrytypebt "Direct link to countrytypebt")

Bhutan

#### [`CountryType.BW`](#)[​](#countrytypebw "Direct link to countrytypebw")

Botswana

#### [`CountryType.BY`](#)[​](#countrytypeby "Direct link to countrytypeby")

Belarus

#### [`CountryType.BZ`](#)[​](#countrytypebz "Direct link to countrytypebz")

Belize

#### [`CountryType.CA`](#)[​](#countrytypeca "Direct link to countrytypeca")

Canada

#### [`CountryType.CD`](#)[​](#countrytypecd "Direct link to countrytypecd")

Congo, The Democratic Republic of the

#### [`CountryType.CG`](#)[​](#countrytypecg "Direct link to countrytypecg")

Congo

#### [`CountryType.CH`](#)[​](#countrytypech "Direct link to countrytypech")

Switzerland

#### [`CountryType.CI`](#)[​](#countrytypeci "Direct link to countrytypeci")

Côte d'Ivoire

#### [`CountryType.CL`](#)[​](#countrytypecl "Direct link to countrytypecl")

Chile

#### [`CountryType.CM`](#)[​](#countrytypecm "Direct link to countrytypecm")

Cameroon

#### [`CountryType.CN`](#)[​](#countrytypecn "Direct link to countrytypecn")

China

#### [`CountryType.CO`](#)[​](#countrytypeco "Direct link to countrytypeco")

Colombia

#### [`CountryType.CR`](#)[​](#countrytypecr "Direct link to countrytypecr")

Costa Rica

#### [`CountryType.CU`](#)[​](#countrytypecu "Direct link to countrytypecu")

Cuba

#### [`CountryType.CV`](#)[​](#countrytypecv "Direct link to countrytypecv")

Cabo Verde

#### [`CountryType.CW`](#)[​](#countrytypecw "Direct link to countrytypecw")

Curaçao

#### [`CountryType.CY`](#)[​](#countrytypecy "Direct link to countrytypecy")

Cyprus

#### [`CountryType.CZ`](#)[​](#countrytypecz "Direct link to countrytypecz")

Czechia

#### [`CountryType.DE`](#)[​](#countrytypede "Direct link to countrytypede")

Germany

#### [`CountryType.DJ`](#)[​](#countrytypedj "Direct link to countrytypedj")

Djibouti

#### [`CountryType.DK`](#)[​](#countrytypedk "Direct link to countrytypedk")

Denmark

#### [`CountryType.DM`](#)[​](#countrytypedm "Direct link to countrytypedm")

Dominica

#### [`CountryType.DO`](#)[​](#countrytypedo "Direct link to countrytypedo")

Dominican Republic

#### [`CountryType.DZ`](#)[​](#countrytypedz "Direct link to countrytypedz")

Algeria

#### [`CountryType.EC`](#)[​](#countrytypeec "Direct link to countrytypeec")

Ecuador

#### [`CountryType.EE`](#)[​](#countrytypeee "Direct link to countrytypeee")

Estonia

#### [`CountryType.EG`](#)[​](#countrytypeeg "Direct link to countrytypeeg")

Egypt

#### [`CountryType.ES`](#)[​](#countrytypees "Direct link to countrytypees")

Spain

#### [`CountryType.ET`](#)[​](#countrytypeet "Direct link to countrytypeet")

Ethiopia

#### [`CountryType.FI`](#)[​](#countrytypefi "Direct link to countrytypefi")

Finland

#### [`CountryType.FJ`](#)[​](#countrytypefj "Direct link to countrytypefj")

Fiji

#### [`CountryType.FO`](#)[​](#countrytypefo "Direct link to countrytypefo")

Faroe Islands

#### [`CountryType.FR`](#)[​](#countrytypefr "Direct link to countrytypefr")

France

#### [`CountryType.GA`](#)[​](#countrytypega "Direct link to countrytypega")

Gabon

#### [`CountryType.GB`](#)[​](#countrytypegb "Direct link to countrytypegb")

United Kingdom

#### [`CountryType.GD`](#)[​](#countrytypegd "Direct link to countrytypegd")

Grenada

#### [`CountryType.GE`](#)[​](#countrytypege "Direct link to countrytypege")

Georgia

#### [`CountryType.GF`](#)[​](#countrytypegf "Direct link to countrytypegf")

French Guiana

#### [`CountryType.GG`](#)[​](#countrytypegg "Direct link to countrytypegg")

Guernsey

#### [`CountryType.GH`](#)[​](#countrytypegh "Direct link to countrytypegh")

Ghana

#### [`CountryType.GI`](#)[​](#countrytypegi "Direct link to countrytypegi")

Gibraltar

#### [`CountryType.GM`](#)[​](#countrytypegm "Direct link to countrytypegm")

Gambia

#### [`CountryType.GN`](#)[​](#countrytypegn "Direct link to countrytypegn")

Guinea

#### [`CountryType.GP`](#)[​](#countrytypegp "Direct link to countrytypegp")

Guadeloupe

#### [`CountryType.GR`](#)[​](#countrytypegr "Direct link to countrytypegr")

Greece

#### [`CountryType.GT`](#)[​](#countrytypegt "Direct link to countrytypegt")

Guatemala

#### [`CountryType.GU`](#)[​](#countrytypegu "Direct link to countrytypegu")

Guam

#### [`CountryType.GY`](#)[​](#countrytypegy "Direct link to countrytypegy")

Guyana

#### [`CountryType.HK`](#)[​](#countrytypehk "Direct link to countrytypehk")

Hong Kong

#### [`CountryType.HN`](#)[​](#countrytypehn "Direct link to countrytypehn")

Honduras

#### [`CountryType.HR`](#)[​](#countrytypehr "Direct link to countrytypehr")

Croatia

#### [`CountryType.HT`](#)[​](#countrytypeht "Direct link to countrytypeht")

Haiti

#### [`CountryType.HU`](#)[​](#countrytypehu "Direct link to countrytypehu")

Hungary

#### [`CountryType.ID`](#)[​](#countrytypeid "Direct link to countrytypeid")

Indonesia

#### [`CountryType.IE`](#)[​](#countrytypeie "Direct link to countrytypeie")

Ireland

#### [`CountryType.IL`](#)[​](#countrytypeil "Direct link to countrytypeil")

Israel

#### [`CountryType.IM`](#)[​](#countrytypeim "Direct link to countrytypeim")

Isle of Man

#### [`CountryType.IN`](#)[​](#countrytypein "Direct link to countrytypein")

India

#### [`CountryType.IQ`](#)[​](#countrytypeiq "Direct link to countrytypeiq")

Iraq

#### [`CountryType.IR`](#)[​](#countrytypeir "Direct link to countrytypeir")

Iran, Islamic Republic of

#### [`CountryType.IS`](#)[​](#countrytypeis "Direct link to countrytypeis")

Iceland

#### [`CountryType.IT`](#)[​](#countrytypeit "Direct link to countrytypeit")

Italy

#### [`CountryType.JE`](#)[​](#countrytypeje "Direct link to countrytypeje")

Jersey

#### [`CountryType.JM`](#)[​](#countrytypejm "Direct link to countrytypejm")

Jamaica

#### [`CountryType.JO`](#)[​](#countrytypejo "Direct link to countrytypejo")

Jordan

#### [`CountryType.JP`](#)[​](#countrytypejp "Direct link to countrytypejp")

Japan

#### [`CountryType.KE`](#)[​](#countrytypeke "Direct link to countrytypeke")

Kenya

#### [`CountryType.KG`](#)[​](#countrytypekg "Direct link to countrytypekg")

Kyrgyzstan

#### [`CountryType.KH`](#)[​](#countrytypekh "Direct link to countrytypekh")

Cambodia

#### [`CountryType.KN`](#)[​](#countrytypekn "Direct link to countrytypekn")

Saint Kitts and Nevis

#### [`CountryType.KR`](#)[​](#countrytypekr "Direct link to countrytypekr")

Korea, Republic of

#### [`CountryType.KW`](#)[​](#countrytypekw "Direct link to countrytypekw")

Kuwait

#### [`CountryType.KY`](#)[​](#countrytypeky "Direct link to countrytypeky")

Cayman Islands

#### [`CountryType.KZ`](#)[​](#countrytypekz "Direct link to countrytypekz")

Kazakhstan

#### [`CountryType.LA`](#)[​](#countrytypela "Direct link to countrytypela")

Lao People's Democratic Republic

#### [`CountryType.LB`](#)[​](#countrytypelb "Direct link to countrytypelb")

Lebanon

#### [`CountryType.LC`](#)[​](#countrytypelc "Direct link to countrytypelc")

Saint Lucia

#### [`CountryType.LI`](#)[​](#countrytypeli "Direct link to countrytypeli")

Liechtenstein

#### [`CountryType.LK`](#)[​](#countrytypelk "Direct link to countrytypelk")

Sri Lanka

#### [`CountryType.LR`](#)[​](#countrytypelr "Direct link to countrytypelr")

Liberia

#### [`CountryType.LS`](#)[​](#countrytypels "Direct link to countrytypels")

Lesotho

#### [`CountryType.LT`](#)[​](#countrytypelt "Direct link to countrytypelt")

Lithuania

#### [`CountryType.LU`](#)[​](#countrytypelu "Direct link to countrytypelu")

Luxembourg

#### [`CountryType.LV`](#)[​](#countrytypelv "Direct link to countrytypelv")

Latvia

#### [`CountryType.LY`](#)[​](#countrytypely "Direct link to countrytypely")

Libya

#### [`CountryType.MA`](#)[​](#countrytypema "Direct link to countrytypema")

Morocco

#### [`CountryType.MC`](#)[​](#countrytypemc "Direct link to countrytypemc")

Monaco

#### [`CountryType.MD`](#)[​](#countrytypemd "Direct link to countrytypemd")

Moldova, Republic of

#### [`CountryType.ME`](#)[​](#countrytypeme "Direct link to countrytypeme")

Montenegro

#### [`CountryType.MG`](#)[​](#countrytypemg "Direct link to countrytypemg")

Madagascar

#### [`CountryType.MK`](#)[​](#countrytypemk "Direct link to countrytypemk")

North Macedonia

#### [`CountryType.ML`](#)[​](#countrytypeml "Direct link to countrytypeml")

Mali

#### [`CountryType.MM`](#)[​](#countrytypemm "Direct link to countrytypemm")

Myanmar

#### [`CountryType.MN`](#)[​](#countrytypemn "Direct link to countrytypemn")

Mongolia

#### [`CountryType.MO`](#)[​](#countrytypemo "Direct link to countrytypemo")

Macao

#### [`CountryType.MQ`](#)[​](#countrytypemq "Direct link to countrytypemq")

Martinique

#### [`CountryType.MR`](#)[​](#countrytypemr "Direct link to countrytypemr")

Mauritania

#### [`CountryType.MS`](#)[​](#countrytypems "Direct link to countrytypems")

Montserrat

#### [`CountryType.MT`](#)[​](#countrytypemt "Direct link to countrytypemt")

Malta

#### [`CountryType.MU`](#)[​](#countrytypemu "Direct link to countrytypemu")

Mauritius

#### [`CountryType.MV`](#)[​](#countrytypemv "Direct link to countrytypemv")

Maldives

#### [`CountryType.MW`](#)[​](#countrytypemw "Direct link to countrytypemw")

Malawi

#### [`CountryType.MX`](#)[​](#countrytypemx "Direct link to countrytypemx")

Mexico

#### [`CountryType.MY`](#)[​](#countrytypemy "Direct link to countrytypemy")

Malaysia

#### [`CountryType.MZ`](#)[​](#countrytypemz "Direct link to countrytypemz")

Mozambique

#### [`CountryType.NA`](#)[​](#countrytypena "Direct link to countrytypena")

Namibia

#### [`CountryType.NC`](#)[​](#countrytypenc "Direct link to countrytypenc")

New Caledonia

#### [`CountryType.NG`](#)[​](#countrytypeng "Direct link to countrytypeng")

Nigeria

#### [`CountryType.NI`](#)[​](#countrytypeni "Direct link to countrytypeni")

Nicaragua

#### [`CountryType.NL`](#)[​](#countrytypenl "Direct link to countrytypenl")

Netherlands

#### [`CountryType.NO`](#)[​](#countrytypeno "Direct link to countrytypeno")

Norway

#### [`CountryType.NP`](#)[​](#countrytypenp "Direct link to countrytypenp")

Nepal

#### [`CountryType.NZ`](#)[​](#countrytypenz "Direct link to countrytypenz")

New Zealand

#### [`CountryType.OM`](#)[​](#countrytypeom "Direct link to countrytypeom")

Oman

#### [`CountryType.PA`](#)[​](#countrytypepa "Direct link to countrytypepa")

Panama

#### [`CountryType.PE`](#)[​](#countrytypepe "Direct link to countrytypepe")

Peru

#### [`CountryType.PF`](#)[​](#countrytypepf "Direct link to countrytypepf")

French Polynesia

#### [`CountryType.PG`](#)[​](#countrytypepg "Direct link to countrytypepg")

Papua New Guinea

#### [`CountryType.PH`](#)[​](#countrytypeph "Direct link to countrytypeph")

Philippines

#### [`CountryType.PK`](#)[​](#countrytypepk "Direct link to countrytypepk")

Pakistan

#### [`CountryType.PL`](#)[​](#countrytypepl "Direct link to countrytypepl")

Poland

#### [`CountryType.PR`](#)[​](#countrytypepr "Direct link to countrytypepr")

Puerto Rico

#### [`CountryType.PS`](#)[​](#countrytypeps "Direct link to countrytypeps")

Palestine, State of

#### [`CountryType.PT`](#)[​](#countrytypept "Direct link to countrytypept")

Portugal

#### [`CountryType.PY`](#)[​](#countrytypepy "Direct link to countrytypepy")

Paraguay

#### [`CountryType.QA`](#)[​](#countrytypeqa "Direct link to countrytypeqa")

Qatar

#### [`CountryType.RE`](#)[​](#countrytypere "Direct link to countrytypere")

Réunion

#### [`CountryType.RO`](#)[​](#countrytypero "Direct link to countrytypero")

Romania

#### [`CountryType.RS`](#)[​](#countrytypers "Direct link to countrytypers")

Serbia

#### [`CountryType.RU`](#)[​](#countrytyperu "Direct link to countrytyperu")

Russian Federation

#### [`CountryType.RW`](#)[​](#countrytyperw "Direct link to countrytyperw")

Rwanda

#### [`CountryType.SC`](#)[​](#countrytypesc "Direct link to countrytypesc")

Seychelles

#### [`CountryType.SE`](#)[​](#countrytypese "Direct link to countrytypese")

Sweden

#### [`CountryType.SG`](#)[​](#countrytypesg "Direct link to countrytypesg")

Singapore

#### [`CountryType.SI`](#)[​](#countrytypesi "Direct link to countrytypesi")

Slovenia

#### [`CountryType.SK`](#)[​](#countrytypesk "Direct link to countrytypesk")

Slovakia

#### [`CountryType.SL`](#)[​](#countrytypesl "Direct link to countrytypesl")

Sierra Leone

#### [`CountryType.SM`](#)[​](#countrytypesm "Direct link to countrytypesm")

San Marino

#### [`CountryType.SN`](#)[​](#countrytypesn "Direct link to countrytypesn")

Senegal

#### [`CountryType.SO`](#)[​](#countrytypeso "Direct link to countrytypeso")

Somalia

#### [`CountryType.SR`](#)[​](#countrytypesr "Direct link to countrytypesr")

Suriname

#### [`CountryType.SS`](#)[​](#countrytypess "Direct link to countrytypess")

South Sudan

#### [`CountryType.ST`](#)[​](#countrytypest "Direct link to countrytypest")

Sao Tome and Principe

#### [`CountryType.SV`](#)[​](#countrytypesv "Direct link to countrytypesv")

El Salvador

#### [`CountryType.SX`](#)[​](#countrytypesx "Direct link to countrytypesx")

Sint Maarten (Dutch part)

#### [`CountryType.SY`](#)[​](#countrytypesy "Direct link to countrytypesy")

Syrian Arab Republic

#### [`CountryType.SZ`](#)[​](#countrytypesz "Direct link to countrytypesz")

Eswatini

#### [`CountryType.TC`](#)[​](#countrytypetc "Direct link to countrytypetc")

Turks and Caicos Islands

#### [`CountryType.TG`](#)[​](#countrytypetg "Direct link to countrytypetg")

Togo

#### [`CountryType.TH`](#)[​](#countrytypeth "Direct link to countrytypeth")

Thailand

#### [`CountryType.TJ`](#)[​](#countrytypetj "Direct link to countrytypetj")

Tajikistan

#### [`CountryType.TN`](#)[​](#countrytypetn "Direct link to countrytypetn")

Tunisia

#### [`CountryType.TR`](#)[​](#countrytypetr "Direct link to countrytypetr")

Turkey

#### [`CountryType.TT`](#)[​](#countrytypett "Direct link to countrytypett")

Trinidad and Tobago

#### [`CountryType.TW`](#)[​](#countrytypetw "Direct link to countrytypetw")

Taiwan, Province of China

#### [`CountryType.TZ`](#)[​](#countrytypetz "Direct link to countrytypetz")

United Republic of Tanzania

#### [`CountryType.UA`](#)[​](#countrytypeua "Direct link to countrytypeua")

Ukraine

#### [`CountryType.UG`](#)[​](#countrytypeug "Direct link to countrytypeug")

Uganda

#### [`CountryType.US`](#)[​](#countrytypeus "Direct link to countrytypeus")

United States of America

#### [`CountryType.UY`](#)[​](#countrytypeuy "Direct link to countrytypeuy")

Uruguay

#### [`CountryType.UZ`](#)[​](#countrytypeuz "Direct link to countrytypeuz")

Uzbekistan

#### [`CountryType.VC`](#)[​](#countrytypevc "Direct link to countrytypevc")

Saint Vincent and the Grenadines

#### [`CountryType.VE`](#)[​](#countrytypeve "Direct link to countrytypeve")

Bolivarian Republic of Venezuela

#### [`CountryType.VG`](#)[​](#countrytypevg "Direct link to countrytypevg")

Virgin Islands, British

#### [`CountryType.VI`](#)[​](#countrytypevi "Direct link to countrytypevi")

Virgin Islands, U.S.

#### [`CountryType.VN`](#)[​](#countrytypevn "Direct link to countrytypevn")

Vietnam

#### [`CountryType.WS`](#)[​](#countrytypews "Direct link to countrytypews")

Samoa

#### [`CountryType.YT`](#)[​](#countrytypeyt "Direct link to countrytypeyt")

Mayotte

#### [`CountryType.ZA`](#)[​](#countrytypeza "Direct link to countrytypeza")

South Africa

#### [`CountryType.ZM`](#)[​](#countrytypezm "Direct link to countrytypezm")

Zambia

#### [`CountryType.ZW`](#)[​](#countrytypezw "Direct link to countrytypezw")

Zimbabwe

### Member Of[​](#member-of "Direct link to Member Of")

[`proxy`](/bql-schema/operations/mutations/proxy) mutation

---

## Enum: LiveURLStreamType
Source: https://docs.browserless.io/bql-schema/types/enums/live-url-stream-type

Error: 404 Client Error: Not Found for url: https://docs.browserless.io/bql-schema/types/enums/liveurlstreamtype


---

## Enum: Method
Source: https://docs.browserless.io/bql-schema/types/enums/method

* * Types* Enums* Method

Open in ChatGPT

On this page

# Method

The various HTTP-based methods to wait for

```
enum Method {  
  CONNECT  
  DELETE  
  GET  
  HEAD  
  OPTIONS  
  PATCH  
  POST  
  PUT  
  TRACE  
}
```

### Values[​](#values "Direct link to Values")

#### [`Method.CONNECT`](#)[​](#methodconnect "Direct link to methodconnect")

#### [`Method.DELETE`](#)[​](#methoddelete "Direct link to methoddelete")

#### [`Method.GET`](#)[​](#methodget "Direct link to methodget")

#### [`Method.HEAD`](#)[​](#methodhead "Direct link to methodhead")

#### [`Method.OPTIONS`](#)[​](#methodoptions "Direct link to methodoptions")

#### [`Method.PATCH`](#)[​](#methodpatch "Direct link to methodpatch")

#### [`Method.POST`](#)[​](#methodpost "Direct link to methodpost")

#### [`Method.PUT`](#)[​](#methodput "Direct link to methodput")

#### [`Method.TRACE`](#)[​](#methodtrace "Direct link to methodtrace")

### Member Of[​](#member-of "Direct link to Member Of")

[`proxy`](/bql-schema/operations/mutations/proxy) mutation ● [`reject`](/bql-schema/operations/mutations/reject) mutation ● [`request`](/bql-schema/operations/mutations/request) mutation ● [`RequestInput`](/bql-schema/types/inputs/request-input) input ● [`RequestResponse`](/bql-schema/types/objects/request-response) object ● [`response`](/bql-schema/operations/mutations/response) mutation ● [`ResponseResponse`](/bql-schema/types/objects/response-response) object ● [`waitForRequest`](/bql-schema/operations/mutations/wait-for-request) mutation

---

## Enum: OperatorTypes
Source: https://docs.browserless.io/bql-schema/types/enums/operator-types

* * Types* Enums* OperatorTypes

Open in ChatGPT

On this page

# OperatorTypes

Logical operators for APIs that have conditions

```
enum OperatorTypes {  
  and  
  or  
}
```

### Values[​](#values "Direct link to Values")

#### [`OperatorTypes.and`](#)[​](#operatortypesand "Direct link to operatortypesand")

"and" logical operator

#### [`OperatorTypes.or`](#)[​](#operatortypesor "Direct link to operatortypesor")

"or" logical operator

### Member Of[​](#member-of "Direct link to Member Of")

[`proxy`](/bql-schema/operations/mutations/proxy) mutation ● [`reject`](/bql-schema/operations/mutations/reject) mutation ● [`request`](/bql-schema/operations/mutations/request) mutation ● [`response`](/bql-schema/operations/mutations/response) mutation

---

## Enum: PDFPageFormat
Source: https://docs.browserless.io/bql-schema/types/enums/pdf-page-format

Error: 404 Client Error: Not Found for url: https://docs.browserless.io/bql-schema/types/enums/pdfpageformat


---

## Enum: ResourceType
Source: https://docs.browserless.io/bql-schema/types/enums/resource-type

* * Types* Enums* ResourceType

Open in ChatGPT

On this page

# ResourceType

The type of resource for a given network or HTTP request

```
enum ResourceType {  
  cspviolationreport  
  document  
  eventsource  
  fetch  
  font  
  image  
  manifest  
  media  
  other  
  ping  
  prefetch  
  preflight  
  script  
  signedexchange  
  stylesheet  
  texttrack  
  websocket  
  xhr  
}
```

### Values[​](#values "Direct link to Values")

#### [`ResourceType.cspviolationreport`](#)[​](#resourcetypecspviolationreport "Direct link to resourcetypecspviolationreport")

#### [`ResourceType.document`](#)[​](#resourcetypedocument "Direct link to resourcetypedocument")

#### [`ResourceType.eventsource`](#)[​](#resourcetypeeventsource "Direct link to resourcetypeeventsource")

#### [`ResourceType.fetch`](#)[​](#resourcetypefetch "Direct link to resourcetypefetch")

#### [`ResourceType.font`](#)[​](#resourcetypefont "Direct link to resourcetypefont")

#### [`ResourceType.image`](#)[​](#resourcetypeimage "Direct link to resourcetypeimage")

#### [`ResourceType.manifest`](#)[​](#resourcetypemanifest "Direct link to resourcetypemanifest")

#### [`ResourceType.media`](#)[​](#resourcetypemedia "Direct link to resourcetypemedia")

#### [`ResourceType.other`](#)[​](#resourcetypeother "Direct link to resourcetypeother")

#### [`ResourceType.ping`](#)[​](#resourcetypeping "Direct link to resourcetypeping")

#### [`ResourceType.prefetch`](#)[​](#resourcetypeprefetch "Direct link to resourcetypeprefetch")

#### [`ResourceType.preflight`](#)[​](#resourcetypepreflight "Direct link to resourcetypepreflight")

#### [`ResourceType.script`](#)[​](#resourcetypescript "Direct link to resourcetypescript")

#### [`ResourceType.signedexchange`](#)[​](#resourcetypesignedexchange "Direct link to resourcetypesignedexchange")

#### [`ResourceType.stylesheet`](#)[​](#resourcetypestylesheet "Direct link to resourcetypestylesheet")

#### [`ResourceType.texttrack`](#)[​](#resourcetypetexttrack "Direct link to resourcetypetexttrack")

#### [`ResourceType.websocket`](#)[​](#resourcetypewebsocket "Direct link to resourcetypewebsocket")

#### [`ResourceType.xhr`](#)[​](#resourcetypexhr "Direct link to resourcetypexhr")

### Member Of[​](#member-of "Direct link to Member Of")

[`proxy`](/bql-schema/operations/mutations/proxy) mutation ● [`reject`](/bql-schema/operations/mutations/reject) mutation ● [`request`](/bql-schema/operations/mutations/request) mutation ● [`RequestResponse`](/bql-schema/types/objects/request-response) object ● [`response`](/bql-schema/operations/mutations/response) mutation ● [`ResponseResponse`](/bql-schema/types/objects/response-response) object

---

## Enum: ScreenshotType
Source: https://docs.browserless.io/bql-schema/types/enums/screenshot-type

* * Types* Enums* ScreenshotType

Open in ChatGPT

On this page

# ScreenshotType

The different types of screenshot formats

```
enum ScreenshotType {  
  jpeg  
  png  
  webp  
}
```

### Values[​](#values "Direct link to Values")

#### [`ScreenshotType.jpeg`](#)[​](#screenshottypejpeg "Direct link to screenshottypejpeg")

JPEG image format

#### [`ScreenshotType.png`](#)[​](#screenshottypepng "Direct link to screenshottypepng")

PNG image format

#### [`ScreenshotType.webp`](#)[​](#screenshottypewebp "Direct link to screenshottypewebp")

WebP image format

### Member Of[​](#member-of "Direct link to Member Of")

[`screenshot`](/bql-schema/operations/mutations/screenshot) mutation

---

## Enum: VerifyTypes
Source: https://docs.browserless.io/bql-schema/types/enums/verify-types

* * Types* Enums* VerifyTypes

Open in ChatGPT

On this page

# VerifyTypes

The different types of verification methods that can be bypassed

```
enum VerifyTypes {  
  cloudflare  
}
```

### Values[​](#values "Direct link to Values")

#### [`VerifyTypes.cloudflare`](#)[​](#verifytypescloudflare "Direct link to verifytypescloudflare")

Cloudflare protection

### Member Of[​](#member-of "Direct link to Member Of")

[`verify`](/bql-schema/operations/mutations/verify) mutation

---

## Enum: WaitUntilGoto
Source: https://docs.browserless.io/bql-schema/types/enums/wait-until-goto

* * Types* Enums* WaitUntilGoto

Open in ChatGPT

On this page

# WaitUntilGoto

Options for when to consider the page has loaded and proceed with further execution

```
enum WaitUntilGoto {  
  commit  
  load  
  domContentLoaded  
  firstMeaningfulPaint  
  firstContentfulPaint  
  interactiveTime  
  networkIdle  
}
```

### Values[​](#values "Direct link to Values")

#### [`WaitUntilGoto.commit`](#)[​](#waituntilgotocommit "Direct link to waituntilgotocommit")

Fired when network response is received and the document has started loading

#### [`WaitUntilGoto.load`](#)[​](#waituntilgotoload "Direct link to waituntilgotoload")

Fired when the JavaScript 'load' event occurs

#### [`WaitUntilGoto.domContentLoaded`](#)[​](#waituntilgotodomcontentloaded "Direct link to waituntilgotodomcontentloaded")

Fired when the DOMContentLoaded event is fired

#### [`WaitUntilGoto.firstMeaningfulPaint`](#)[​](#waituntilgotofirstmeaningfulpaint "Direct link to waituntilgotofirstmeaningfulpaint")

Indicates when the primary content of a page is visible to the user

#### [`WaitUntilGoto.firstContentfulPaint`](#)[​](#waituntilgotofirstcontentfulpaint "Direct link to waituntilgotofirstcontentfulpaint")

The render time of the largest image or text block visible in the viewport, relative to when the user first navigated to the page

#### [`WaitUntilGoto.interactiveTime`](#)[​](#waituntilgotointeractivetime "Direct link to waituntilgotointeractivetime")

Use with caution: Chrome's best guess as to when the page becomes interactable

#### [`WaitUntilGoto.networkIdle`](#)[​](#waituntilgotonetworkidle "Direct link to waituntilgotonetworkidle")

Use with caution: Fired when there are no more than 2 network connections for at least 500 ms

### Member Of[​](#member-of "Direct link to Member Of")

[`goto`](/bql-schema/operations/mutations/goto) mutation ● [`switchToWindow`](/bql-schema/operations/mutations/switch-to-window) mutation ● [`waitForNavigation`](/bql-schema/operations/mutations/wait-for-navigation) mutation

---

## Enum: WaitUntilHistory
Source: https://docs.browserless.io/bql-schema/types/enums/wait-until-history

* * Types* Enums* WaitUntilHistory

Open in ChatGPT

On this page

# WaitUntilHistory

The different stages of the browser's loading process

```
enum WaitUntilHistory {  
  commit  
  domContentLoaded  
  load  
  networkIdle  
}
```

### Values[​](#values "Direct link to Values")

#### [`WaitUntilHistory.commit`](#)[​](#waituntilhistorycommit "Direct link to waituntilhistorycommit")

Fired when network response is received and the document started loading

#### [`WaitUntilHistory.domContentLoaded`](#)[​](#waituntilhistorydomcontentloaded "Direct link to waituntilhistorydomcontentloaded")

Fired when the DOMContentLoaded event is fired

#### [`WaitUntilHistory.load`](#)[​](#waituntilhistoryload "Direct link to waituntilhistoryload")

Fired when the 'load' event occurs

#### [`WaitUntilHistory.networkIdle`](#)[​](#waituntilhistorynetworkidle "Direct link to waituntilhistorynetworkidle")

Use with caution: Fired when there are no network connections for at least 500 ms

### Member Of[​](#member-of "Direct link to Member Of")

[`back`](/bql-schema/operations/mutations/back) mutation ● [`content`](/bql-schema/operations/mutations/content) mutation ● [`forward`](/bql-schema/operations/mutations/forward) mutation ● [`reload`](/bql-schema/operations/mutations/reload) mutation