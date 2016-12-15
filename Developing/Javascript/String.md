# Remove punctuations

<pre>
<code>
var str="jfkldsjalk,.23@#!$$k~!  @#$%^&*()(_+-=|\{}[]';:,./<>??gg  g~```gf";
str=str.replace(/[\ |\~|\`|\!|\@|\#|\$|\%|\^|\&|\*|\(|\)|\-|\_|\+|\=|\||\\|\[|\]|\{|\}|\;|\:|\"|\'|\,|\<|\.|\>|\/|\?]/g,"");

console.log(str)
</code>
</pre>