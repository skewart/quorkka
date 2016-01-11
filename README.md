# Quorkka
A Quora question generator

### About

Quorkka generates fake Quora questions via a Markov chain. I made it one evening while eating Mexican pizza and drinking several glasses of wine.

Quorkka = quokka + Quora.  That's all.

### Usage

Install the gem.

```text
$ gem install quorkka
```

Or add to your Gemfile.

```ruby
gem 'quorkka', '~> 0.0.1'
```

Use the CLI to print a question to stdout.

```text
$ quorkka
> I currently have $100 in savings. I would like to become a millionaire in one week. What should I do?
```

Or include the gem.  The only publicly exposed method is `Quorkka#question`, which returns a question.

```ruby
require 'quorkka'

q = Quorkka.question
puts q
# 'What country has the worst pigeons?'
```

### Configuration

There is no configuration - at least not currently.  

You can change the questions used to build the Markov chain though. These live in file(s) in the /resources/questions directory.
To add more questions to the input set simply add more question files to this directory.  Each question should be on its own line.
All files in the directory are treated as question input files. 

```text
NNMOZMZDMDODMD88DO7N8$8DD77=8?ODDNNODDN$O+M8DD8DDZIM8NDNDMMD8M~?88NN8NND87NDDZNZZM8NONM8ND888D8DNMMN
8O7NI8DNMMMMN?N8O$Z8$?OD$$$Z$Z8$8M8Z8DN7NZ88MN88DODDM$N8DMMM7MNMOZNDOO8NMNNN8$DI8$DODO8ONNDDD8DMMMMM
=I$$OMN7N8N8$M88$$O~DO8?IZ:$I$77Z7ZO8NMM$NOD$NMZN8ND8M8ZDNMNMDM8NMN88D8ZNDNDONDMDZO8DZDMD8ND8DNNMMMM
ZIDMZND8MNMO7=78I=$7:??.??877+$7NN=8ND8MNNZ$MM8NDMNNDNMONDMNNMMNNN88ND8NNMNMDDNND8DNNMN8NDO8D8DMNNDZ
?M+OOMN8ONDI7OMO8N88MMOOZIZ7?$?$$NMDNNNNDMII=8DD$DN8DNNNMNMMD8MONNMNDMMNMMNMMMNNDDMDNMNNMD8NN8NDNDOD
$M8NDNDDZ8ZDZOOD88NMMZDMOZZDODOODI8MO8NDNMDODMMDONNOMNMMNONMMDDM87=7NNZDNMMMNMMMMMMNNNMDNNNN8MDND$N8
88NODDNDIO8NO$ZND8NMNMMMNON8ZO8ZNMDMDD?M8MMMNNNNMMMMMMD8O?=:~,ND8DZ88OZNDDN8MNMMNZODMMMNNMMMMMNND8ND
8DDNMNNDZ8NN?NNDNZDMMN8MD8MMM+M8ZOO7???+?$8Z88OMNMNMND7??I+++:~?DDN$OMOD8888D8$NMNNNNMMMMNN8NNNDDNO8
NNMDDMO$ONMMMDDMMNMNNMMDDDMD8IMZO$II+++==+==?7II$+7$I$?+??II?=~Z?$ZDN$N8DNDO8ZI8O8DNMMMNM88MDMDNMMNN
NNMMDMMMMNMM8MMMDM8NNNMNMMDMNNN8Z++?7?~I++?=?=+I~====?~~?+:??I?+I8DNOD8D8NZ8NIOD88DNMDMNN78DMDNDDDNM
NNOMMNMMMMNDNNNMNMMNMMNMMNMMOMM?+?IZ$7I~??7$?+I++I++~~?=I:+?+I7I$ODN8DONDOOONNNNNN8NMMIMMN8NNMDZNNNN
NNMNMMNNNMNMMNMMMMMMMNMMMMMZNNN+~+??7$$IIII?7I?+I+?+I?I7~+I=I?+?++7NNNNNM8NNNNNNNMM=ID$8DMMDNDMMDMMN
DNDNDNDNNNMNNNMMMNNMMMMMMMMMMMM===???7+I?+??II??I$?77I+++?I=?$?=:+IZ8MMMMMMMNNMMNMNN8ZMNNMNMMNMNNDDN
O8ODOO8DDDDND8888O?DNNMMDNNMNDDD+=+II77?+$?7???$ZZZ$7?7$777?++$IN8?7Z8D8NNNNMNNMMMMODNMDMMMMMMMMMND8
8D888NZ~8$DDDDDD8M888ZODDZDDD8DZ?7?77+???II$N8DZZ$7III?I77$$I?7?N$+??Z8NNNNNMDNNMNMMMMMMMMMMMNNMMDZ$
I?I$II$8Z~=,::~:I+$Z$IO88NO8$88$77$7I?+I7I?M7$IMZ7+II7IIZOOOZOOZ7OOI++?Z8$8NDNNMMNNNNNMMMMMMMMMMMNMM
=I+I$$.,7$I$7IO7Z8$7$$D$O?+=7$$Z$7$77I??777OOOZO8ZZII??OOOZ$$$$$I$Z87?~~IZ+?7~I~:=+IZ888NDNNNDDDMMMN
++7Z$O$7~:7~I$+7ZZ++777II?$Z7MDN8?I77?+==+=+=7Z8OZ$777$Z$OZOO88ZO?$$$OI?II77D77I7?I=~++~==+I?$$Z$7?:
I7I7O$O8O$+~?I7$?7??Z77$$77$+I+++:?I+II=+7$8$Z8$$$I++IOODD88NN8DD$7$Z87I+~::,:,..+~,=~~~,:,.......,.
$$O$7$$Z88?II?$+??II???=$+?==~+,==:II77I77$OZ7?$$I+7778ODD8DNDD8ZO?I?7?$7I:......,..............,...
8ONDZ$I8NOZ$?++?I?7~~+=~::+:,++?~I,II?I77$ZO$O$$I????$O88O8DNDD8D$?+II?I7?=.................,.......
++,?,::~=:,.:,,~:~::,,:..:,..=.,.:~IIII777I$Z$?I??I?7I$Z8DNNDND8OI=??+777II:.........,,.:.,,,,:.,.,.
.:~+=Z=:+.::~+.7,?,,:=.:.,.......,=+7?II7$III7I??+I+++IIZO8DDDD8I=7$$Z$$$7I=.. .. .,,.~::,.,,::,,,:.
..=,,,:,:=,,,..:..,,:..:...+.....I?7?77?III?7??Z$7IZZ$III$O88D8$77$Z$$$$$7?,.... .:,.=:.,::~~~,~$:~,
.~~.,7+:~,~,,.,~=:,,..,,..~:...:IZ??IIOZ$I7$?Z7$7$$$7$$Z8ODDDDZII?$$7Z$77?=,......~,,~:,+?+:~===.:+?
7$.,:,...,:.,.,...7~=..+II=...+78II?$I$$7I77???I$I7+??I?77$Z$IIIII?I$7$$II=,...::,::~,===.,++~???=+7
++=7,..,:I==,,...............O$OOZI?I$I?77II?II$II?I$II77$$O$77$II$Z$7I7+:,::,,.....+=+:?=:~~+~:I=++
:.....,?,.....:  ...,..  ..:O7Z$Z77+?I$I?+III?I+I7II777777I$77I77777$$7+::,:~.:.:~==+~~:+??=~?=~+=7=
,,....,.= :,,,...... .....~8ZO8OO77?++?I????+++II?7+7I7$$7$$$$7$7I$7II+=...~I?~~.7,??~=$?==I7=?I+?7I
.,,,....  .........,.,..:=ZDD8OZ7O7$?+=?++???=??III?I?$$$7777?$7II7I?+:~~~=,~~~=I~~=~~+I+77ZIZ7$????
......  ,  ..,.:..,,+:..:ODZO8OZ$$7$ZI+=+I7??+7??I???7Z$O$$$7III???7?++=+~~:=?:?~~:7++7I77I?+~Z$7?I+
....., .. ....=~:~,:...=ZD8ZZOZ$$$I$$7?===I???+?III7I7$Z$Z$$I?I?I$77I?~=~:++==:I??+7+$?I???I??I+?II7
...:,+....,..,,,+.:=,:IODD8ZOZ777?$OZZ$7II77?II7?7$O$$$I77I777Z7O$$O7I~:~~===+=+II++II==?I+?$?+?~I??
:..,.,:.,,:,..=$,,:,,:O8Z8ZODZ777III?Z7Z7$7I777$7I$I7$7I7$7$7$ZOOZ$ZI7+=:?==:I+,?7?==I++I+7I+I+===7I
.,..,~,=~:,::.+,...=~Z8O88DZZ$$I7I7Z7$O$$OZ$7$$$$77I7?7$7$ZDOO$OZOO$II?=~=++~7=?=?=+????=??I+7?++?+$
..,~,~:I:?,,:.I~:?==?ZD8OO8Z$7$7I$ZI$Z$ZZZ$Z$7ZI$Z$I$$O$$O$O87OOZZZ77I::=:~??=~~?=:++7++I7?~?+7=??I?
+.=+~I?7I:,.,=?=I:..78O8OZZZO77$7I77I$IIZI7877Z7Z$I7$$IIZZOOZO$Z$$Z7$?~~~.=~=?==?+=+?I+II~+=+I+I7$=7
,Z...,,,:=:,,,,:.,.=O8OODZODO7IZ$IIO$I7$ZI$$Z$Z77I$$Z7Z$ZZ$$$7$7$ZZI$I:.==~~+??~,~?~~~+???=?+=+=:??+
......:,.+,.,~,=+=:~8OZ$ZZOI$7?$$?7Z7Z?II7OZIZ7$$?$ZZ$8OZOZDNN888OIZ7+,=~~:?===:~+~+=++++=+?7+=??~:,
:,.::~?+:,.,.:,:=::IO88ZOZ7$II?I7?77I$7+ZI$II?ZZZZ$88ZDZO88NND888$ZI+~~~=+,+=~+~=~?~+?=II=+==+?+?+?+
,,,=+IZO~::?~?~:I~,IOO$O$$Z7$II?+Z7Z$ZO8ZZ88Z$7$8OZ88O8DD88DDDZZZ877~~=:.,~~::~:I:=+?I+=+??~++:7+=~~
+?.,?,:,?+=?=:+,~+:?O$ZZ$D$$$$$?+7IZ$8OZ$D88ON8OOOODDO8NN8DD8O$ZZ$7?:=:=:~:,===~?.=+=~,++=I=I=?==:+=
Z7?..+7:II:.,:,~:I.+8ZO$7OZ8Z7II+?$888II8INOZOZ8OO888DDDZ$O$O$7ZOZ+~:~:~==~.+~~+,I==,=++,I=?=~???+=~
~Z=O:+:~$=:=+~?:==~=OII7I8ZOO77I==?$77Z78$O78Z$O8O88O888ZO$8$$8O$7,:,~~:,~=,=~==:::++===+=?=+I?,=?.I
~?:I?$7+7??I==?~?I:=7Z$$Z7$IZZ$77??=?I77$OO7+Z8ZOZOO$Z$ZI$IZ?$$87~=,.,::+=,~~~7~=~~=~?,+=+~,,7$=I~=~
::~=+:O=~~::,?I~:+?:I$$Z7Z7$$$O7O7I+++I$NOI77Z?O777I$77$$OZOD8DO?==~:,::,.~,=~~=+::=:=+,::++:=~=?=,=
?7I~I+?I+,II,?=?~:~=+77$$$$Z$OIO78O7Z?=77ZDZIII$7$II?7OO$$ODDN8I++=~+?I+I:+:7?7$$Z$7:?I+?I?$7?$++77Z
?Z?I7~7?~I==:=.=+7I?II7Z$7O7+$$OOZ8$?7$I=IIOOZ$8ZZ7$I78OOODNNND?~=?~,??=$,:II?Z=I77=7I++~=7I$II$+=7$
Z,+=+777?++:?:7$?IZ?Z77$$O$ZOZI7Z$OZ$8$Z7I=I78ODZZ8ZNNDZ8ONNNNZ??I,7++ZI$I+$I+I+I$=7=7Z~+Z?$Z7I~+??I
?I$++7Z~~:+77+$7??$IZ?7$ZOOZOOIZZZOZZ8$8O$I+IONNN8DNNMD8DDNNNN7?=?+?I=$7O??OI7$=+??~?$$OI7IZ~+++7~I7
:~+?7I7++I=7IOI$7I?+~~I$OOOZZZZO$$OZOO7O8I?7I8NDNMDNDMDM8DNMM87+?=~O$=++$II~II?77II=I?7$Z?7I7ZZ+O+:$
+?=~:??:7I$7OZ7O=7I$7$?7Z$OZ88ZOZZZ7$III77I7$ZDDMNNNNMMNNDMNZ?II==~??+I$II,+?77?+$ZI?I+7?Z?ZZ?I7$OZ?
```