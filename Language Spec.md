```XML

<body> := <instruction>*

<instruction> := <if> | <declare> | <class> | <assignment> | <call> | <macro> | <for> | <while>

<declare> := <class> <variable>|<assignment>;
<assignment> := <variable>=<expression>;

<macro> := <import>|<define>
<import> := #import static? <package>\n
<define> := #define <identifier> [^\n]\n

<if> := if (<expression>) {<body>} <elseif>* <else>?
<elseif> := else if (<expression>) {<body>}
<else> := else {<body>}

<operator> := [ ~!+-/%*^=<> ] <operator>?
<expression> := <immediate> | <variable> | <lambda> | (<expresssion>) | <expression>?<operator><expression\<expression\>?\<operator\>>?
<lambda> := do <instruction> | doreturn <expression> | <arguments> -> {<body>}
<arguments> := () | ( <variable>,* <variable> )

<immediate> := <string>|<char>|<integer>|<long>|<float>|<double>
<string> := "([^"]|(?:\"))*"
<char> := '[^']|\''
<integer> := [0-1] | [1-9][0-9]+ | 0[0-9]+ | 0x[0-9a-f] | 0b[01]
<long> := <integer>l
<float> := .[0-9]+f? | [0-9]+.f? | [0-9]+.[0-9]+f? | <integer>f
<double> := .[0-9]+d | [0-9]+.d | [0-9]+.[0-9]+d | <integer>d

```
