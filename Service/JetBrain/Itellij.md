 - [Intellij IDEA checkstyle](http://stackoverflow.com/questions/26955766/intellij-idea-checkstyle)
    - can use CheckStyle-IDEA plug-in
 - [CodeStandard - 2.14 IDE CheckStyle setup](https://w.888.com/index.php/ELM/YVR-ELM/CodeStandard#IDE_CheckStyle_setup)
 
```
Edit the checkstyle-config.xml file, remove basedir variable and the suppression filter
<property name="basedir" value="${basedir}"/>
and
<module name="SuppressionFilter">
<property name="file" value="${basedir}/configuration/CheckStyle/suppressions.xml"/>
</module>
```