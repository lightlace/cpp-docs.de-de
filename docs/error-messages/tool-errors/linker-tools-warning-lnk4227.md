---
title: Linkertoolwarnung Lnk4227 | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK4227
dev_langs:
- C++
helpviewer_keywords:
- LNK4227
ms.assetid: 941a0414-9964-4e02-8487-f9daa42ef7f9
caps.latest.revision: 11
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: ee566318c7d19159f9a2c084d348b5010a65e2de
ms.lasthandoff: 02/24/2017

---
# <a name="linker-tools-warning-lnk4227"></a>Linkertoolwarnung LNK4227
Warnung bei Metadatenoperation (HRESULT): Warning_message  
  
Der Linker entdeckt Unterschiede in den Metadaten beim Zusammenführen:  
  
-   Eine oder mehrere Assemblys verwiesen wird mit der Assembly, die gerade erstellt wird.  
  
-   Eine oder mehrere Quellcodedateien in einer Kompilierung.  
  
Z. B. LNK4227 kann verursacht werden, wenn zwei globale mit demselben Namen, aber unterschiedlich deklariert Parameterinformationen Funktionen (Deklarationen sind nicht konsistent in jeder Kompiliereinheit). Mithilfe von ildasm.exe/Text/Metadata `object_file` auf einzelnen OBJ-Datei, und Sie sollte wie die Typen unterscheiden.  
  
LNK4227 meldet auch Probleme, die mit einem anderen Tool stammen. Z. B. al.exe; finden Sie unter [Al.exe Tool Fehler und Warnungen](http://msdn.microsoft.com/en-us/7f125d49-0a03-47a6-9ba9-d61a679a7d4b).  
  
Probleme mit Metadaten müssen behoben werden, um die Warnung zu vermeiden.  
  
Beispielsweise wird LNK4227 generiert, wenn eine Assembly anders als die Assembly signiert wurde, die darauf verweist.  
  
Im folgende Beispiel wird LNK4227 generiert:  
  
```  
// LNK4227.cpp  
// compile with: /clr  
using namespace System::Reflection;  
  
[assembly:AssemblyDelaySignAttribute(false)];  
  
int main() {}  
```  
  
 Und dann  
  
```  
// LNK4227b.cpp  
// compile with: /clr LNK4227.cpp /FeLNK4227b.exe  
using namespace System::Reflection;  
using namespace System::Runtime::CompilerServices;  
  
[assembly:AssemblyDelaySignAttribute(true)];  
// Try the following line instead  
// [assembly:AssemblyDelaySignAttribute(false)];  
  
ref class MyClass  
{  
};  
```  
  
LNK4227 kann auch generiert werden, wenn Versionsnummern im falschen Format an Assemblyattribute übergeben werden.  Die ' *'-Notation ist für AssemblyVersionAttribute spezifisch.  Um diese Warnung zu beheben, verwenden Sie nur Zahlen in die Versionsattribute AssemblyVersionAttribute.  
  
Im folgende Beispiel wird LNK4227 generiert:  
  
```  
// LNK4227e.cpp  
// compile with: /clr /LD /W1  
using namespace System::Reflection;  
[assembly:AssemblyVersionAttribute("2.3.*")];   // OK  
[assembly:AssemblyFileVersionAttribute("2.3.*")];   // LNK4227  
// try the following line instead  
// [assembly:AssemblyFileVersionAttribute("2.3")];  
```
