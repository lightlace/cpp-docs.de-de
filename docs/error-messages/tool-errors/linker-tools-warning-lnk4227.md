---
title: Linkertoolwarnung Lnk4227 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- LNK4227
dev_langs:
- C++
helpviewer_keywords:
- LNK4227
ms.assetid: 941a0414-9964-4e02-8487-f9daa42ef7f9
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c603110d77b06fac59a725ba448f058bd4ad7a38
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4227"></a>Linkertoolwarnung LNK4227  
  
> Warnung bei Metadatenoperation (*HRESULT*): *Warning_message*  
  
Der Linker hat Unterschiede in den Metadaten festgestellt, beim Zusammenführen von:  
  
-   Eine oder mehrere Assemblys verwiesen wird mit der Assembly, die gerade erstellt wird.  
  
-   Eine oder mehrere Quellcodedateien in einer Kompilierung.  
  
Beispielsweise LNK4227 verursacht sein, wenn Sie zwei globalen Funktionen mit dem gleichen Namen, aber Parameterinformationen anders deklariert haben (d. h. Deklarationen sind nicht konsistent in allen Kompiliereinheit Wert). Mithilfe von ildasm.exe "/ Text" Metadata *Object_file* auf jede OBJ-Datei, um festzustellen, wie sich die Typen unterscheiden.  
  
LNK4227 dient auch zum Melden von Problemen, die mit einem anderen Tool stammen. Suchen Sie nach der Warnmeldung, dass weitere Informationen.  
  
Probleme mit Metadaten müssen behoben werden, um die Warnung zu beheben.  
  
## <a name="example"></a>Beispiel  
  
LNK4227 wird generiert, wenn eine Assembly verwiesen wird anders als die Assembly signiert wurde, die darauf verweist.  
  
Im folgenden Beispiel wird LNK4227 generiert:  
  
```cpp  
// LNK4227.cpp  
// compile with: /clr  
using namespace System::Reflection;  
  
[assembly:AssemblyDelaySignAttribute(false)];  
  
int main() {}  
```  
  
 Und dann  
  
```cpp  
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
  
## <a name="example"></a>Beispiel  
  
LNK4227 kann auch generiert werden, wenn das falsche Format Versionsnummern an Assemblyattribute übergeben werden.  Die ' *' Notation bezieht sich auf die `AssemblyVersionAttribute`.  Um diese Warnung zu beheben, verwenden nur Zahlen in den Attributen Version außer `AssemblyVersionAttribute`.  
  
Im folgenden Beispiel wird LNK4227 generiert:  
  
```cpp  
// LNK4227e.cpp  
// compile with: /clr /LD /W1  
using namespace System::Reflection;  
[assembly:AssemblyVersionAttribute("2.3.*")];   // OK  
[assembly:AssemblyFileVersionAttribute("2.3.*")];   // LNK4227  
// try the following line instead  
// [assembly:AssemblyFileVersionAttribute("2.3")];  
```