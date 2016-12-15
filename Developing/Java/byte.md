 - [java 里面的string 和byte[] 怎么互转？](http://zhidao.baidu.com/link?url=bPO8cK070rqiJHkcSbjC3SEUY3SvXNn-6A1Ezl9Sw-vSLjRr5HjP_1f1eR39HNZmsrlBPgLYmDIrMNNdtbu5iq)
<pre>
Note1: String 可转为 byte[]  --
  String str="abc";
  byte[] data=str.getBytes();  
Note2: byte[] 可转为 String  --
  byte[] data=.....
  String s=new String(data);
Note3:
 为避免发生编码的困扰, 建议不要转成 byte[].
 与char[] 互转比较好.
Note4: String 可转为 char[]  --
  String str = "abc"; 相当於是
  char data[] = {'a', 'b', 'c'};     
  String str = new String(data); 
Note5: char[] 可转为 String  --
  String str="abc";
  char[] data=str.toCharArray();
</pre>
