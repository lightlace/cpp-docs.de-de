---
title: '&lt;Berechtigung&gt; (Visual C++) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- permission
- <permission>
dev_langs:
- C++
helpviewer_keywords:
- <permission> C++ XML tag
- permission C++ XML tag
ms.assetid: 537ee2bc-95bd-48e4-9ce6-3420c3da87f4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: e13824780a5c73d4423bd544a97108b45d1b770a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="ltpermissiongt-visual-c"></a>&lt;Berechtigung&gt; (Visual C++)
Mit dem \<permission>-Tag können Sie den Zugriff auf einen Member dokumentieren. <xref:System.Security.PermissionSet> können Sie den Zugriff auf ein Element angeben.  
  
## <a name="syntax"></a>Syntax  
  
```  
<permission cref="member">description</permission>  
```  
  
#### <a name="parameters"></a>Parameter  
 `member`  
 Ein Verweis auf einen Member oder ein Feld, das von der aktuellen Kompilierungsumgebung aufgerufen werden kann. Der Compiler prüft, ob das angegebene Codeelement vorhanden ist, und übersetzt in der Ausgabe-XML `member` in den kanonischen Elementnamen.  Setzen Sie den Namen in einfache oder doppelte Anführungszeichen.  
  
 Der Compiler gibt eine Warnung aus, wenn er `member` nicht findet.  
  
 Weitere Informationen zum Erstellen eines cref-Verweises auf einen generischen Typ finden Sie unter [\<see>](../ide/see-visual-cpp.md).  
  
 `description`  
 Eine Beschreibung des Zugriffs auf den Member  
  
## <a name="remarks"></a>Hinweise  
 Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) kompiliert werden.  
  
 Der Visual C++-Compiler versucht, cref-Verweise in einem einzigen Durchlauf durch die Dokumentationskommentare aufzulösen.  Bei Verwendung der C++-Suchregeln wird deshalb, wenn ein Symbol vom Compiler nicht gefunden wird, der Verweis als nicht aufgelöst markiert. Finden Sie unter [ \<Seealso >](../ide/seealso-visual-cpp.md) Weitere Informationen.  
  
## <a name="example"></a>Beispiel  
  
```  
// xml_permission_tag.cpp  
// compile with: /clr /doc /LD  
// post-build command: xdcmake xml_permission_tag.dll  
using namespace System;  
/// Text for class TestClass.  
public ref class TestClass {  
   /// <permission cref="System::Security::PermissionSet">Everyone can access this method.</permission>  
   void Test() {}  
};  
```  
  
## <a name="see-also"></a>Siehe auch  
 [XML-Dokumentation](../ide/xml-documentation-visual-cpp.md)