---
title: '&lt;include&gt; (Visual C++) | Microsoft-Dokumentation'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- include
- <include>
dev_langs:
- C++
helpviewer_keywords:
- include C++ XML tag
- <include> C++ XML tag
ms.assetid: 392a3e61-0371-4617-8362-446650876ce3
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b4c1a75acb89d9510dd7f489e5d0d582611da8de
ms.sourcegitcommit: a4454b91d556a3dc43d8755cdcdeabcc9285a20e
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2018
ms.locfileid: "33330426"
---
# <a name="ltincludegt-visual-c"></a>&lt;include&gt; (Visual C++)
Mit dem \<include>-Tag können Sie auf Kommentare in einer anderen Datei verweisen, die die Typen und Member in Ihrem Quellcode beschreiben. Dies ist eine Alternative zum direkten Platzieren von Dokumentationskommentaren in der Quellcodedatei.  Sie können \<include> beispielsweise verwenden, um Standardkommentare einzufügen, die von Ihrem Team bzw. Unternehmen verwendet werden.  
  
## <a name="syntax"></a>Syntax  
  
```  
<include file='filename' path='tagpath' />  
```  
  
#### <a name="parameters"></a>Parameter  
 `filename`  
 Der Name der Datei, die die Dokumentation enthält. Der Dateiname kann mit einem Pfad qualifiziert werden.  Setzen Sie den Namen in einfache oder doppelte Anführungszeichen.  Der Compiler gibt eine Warnung aus, wenn er `filename` nicht findet.  
  
 `tagpath`  
 Ein gültiger XPath-Ausdruck, mit dem der gewünschte in der Datei enthaltene Knotensatz ausgewählt wird.  
  
 `name`  
 Der Namensbezeichner in dem Tag, das sich vor den Kommentaren befindet. `name` besitzt eine `id`.  
  
 `id`  
 Die ID für das Tag, das sich vor den Kommentaren befindet.  Setzen Sie den Namen in einfache oder doppelte Anführungszeichen.  
  
## <a name="remarks"></a>Hinweise  
 Das \<include>-Tag verwendet die XPath-Syntax von XML. Weitere Anpassungsmöglichkeiten mithilfe von \<include> finden Sie in der XPath-Dokumentation.  
  
 Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) kompiliert werden.  
  
## <a name="example"></a>Beispiel  
 Dies ist ein Beispiel einer Mehrfachdatei. Die erste Datei, die \<include> verwendet, enthält die folgenden Dokumentationskommentare:  
  
```  
// xml_include_tag.cpp  
// compile with: /clr /doc /LD  
// post-build command: xdcmake xml_include_tag.dll  
  
/// <include file='xml_include_tag.doc' path='MyDocs/MyMembers[@name="test"]/*' />  
public ref class Test {  
   void TestMethod() {  
   }  
};  
  
/// <include file='xml_include_tag.doc' path='MyDocs/MyMembers[@name="test2"]/*' />  
public ref class Test2 {  
   void Test() {  
   }  
};  
```  
  
 Die zweite Datei, xml_include_tag.doc, enthält die folgenden Dokumentationskommentare:  
  
```  
<MyDocs>  
  
<MyMembers name="test">  
<summary>  
The summary for this type.  
</summary>  
</MyMembers>  
  
<MyMembers name="test2">  
<summary>  
The summary for this other type.  
</summary>  
</MyMembers>  
  
</MyDocs>  
```  
  
## <a name="program-output"></a>Programmausgabe  
  
```  
<?xml version="1.0"?>  
<doc>  
    <assembly>  
        <name>t2</name>  
    </assembly>  
    <members>  
        <member name="T:Test">  
            <summary>  
The summary for this type.  
</summary>  
        </member>  
        <member name="T:Test2">  
            <summary>  
The summary for this other type.  
</summary>  
        </member>  
    </members>  
</doc>  
```  
  
## <a name="see-also"></a>Siehe auch  
 [XML-Dokumentation](../ide/xml-documentation-visual-cpp.md)