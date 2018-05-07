---
title: '&lt;finden Sie unter&gt; (Visual C++) | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-ide
ms.topic: conceptual
f1_keywords:
- <see>
- see
dev_langs:
- C++
helpviewer_keywords:
- <see> C++ XML tag
- see C++ XML tag
ms.assetid: 20ef66f4-b278-45cf-8613-63919edf5720
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a03dd56320b948d47c765f253bf3e6b706ed2b56
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="ltseegt-visual-c"></a>&lt;finden Sie unter&gt; (Visual C++)
Mit dem \<see>-Tag kann ein Link im Text angegeben werden. Verwendung [ \<Seealso >](../ide/seealso-visual-cpp.md) um Text anzugeben, die in einem Abschnitt Siehe auch angezeigt werden sollen.  
  
## <a name="syntax"></a>Syntax  
  
```  
<see cref="member"/>  
```  
  
#### <a name="parameters"></a>Parameter  
 `member`  
 Ein Verweis auf einen Member oder ein Feld, das von der aktuellen Kompilierungsumgebung aufgerufen werden kann.  Setzen Sie den Namen in einfache oder doppelte Anführungszeichen.  
  
 Der Compiler überprüft, dass das angegebene Codeelement vorhanden ist, und löst `member` an den Elementnamen in der XML-Ausgabe.  Der Compiler gibt eine Warnung aus, wenn er `member` nicht findet.  
  
## <a name="remarks"></a>Hinweise  
 Dokumentationskommentare werden zu einer Datei verarbeitet, indem sie mit [/doc](../build/reference/doc-process-documentation-comments-c-cpp.md) kompiliert werden.  
  
 Finden Sie unter [ \<summary >](../ide/summary-visual-cpp.md) ein Beispiel der Verwendung von \<finden Sie unter >.  
  
 Der Visual C++-Compiler versucht, cref-Verweise in einem einzigen Durchlauf durch die Dokumentationskommentare aufzulösen.  Bei Verwendung der C++-Suchregeln wird deshalb, wenn ein Symbol vom Compiler nicht gefunden wird, der Verweis als nicht aufgelöst markiert. Finden Sie unter [ \<Seealso >](../ide/seealso-visual-cpp.md) Weitere Informationen.  
  
## <a name="example"></a>Beispiel  
 Das folgende Beispiel zeigt, wie Sie Cref-Verweis für einen generischen Typ erstellen können, sodass der Compiler den Verweis aufgelöst wird.  
  
```  
// xml_see_cref_example.cpp  
// compile with: /LD /clr /doc  
// the following cref shows how to specify the reference, such that,  
// the compiler will resolve the reference  
/// <see cref="C{T}">  
/// </see>  
ref class A {};  
  
// the following cref shows another way to specify the reference,   
// such that, the compiler will resolve the reference  
/// <see cref="C < T >"/>  
  
// the following cref shows how to hard-code the reference  
/// <see cref="T:C`1">  
/// </see>  
ref class B {};  
  
/// <see cref="A">  
/// </see>  
/// <typeparam name="T"></typeparam>  
generic<class T>  
ref class C {};  
```  
  
## <a name="see-also"></a>Siehe auch  
 [XML-Dokumentation](../ide/xml-documentation-visual-cpp.md)