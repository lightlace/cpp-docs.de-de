---
title: __identifier (C + c++ / CLI) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- __identifier
- __identifier_cpp
dev_langs: C++
helpviewer_keywords: __identifier keyword [C++]
ms.assetid: 348428af-afa7-4ff3-b571-acf874301cf2
caps.latest.revision: "18"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d9eca3bf99c0a798fd31dfa70e00769274a379b5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="identifier-ccli"></a>__identifier (C++/CLI)
Ermöglicht die Verwendung von Visual C++-Schlüsselwörter als Bezeichner an.  
  
## <a name="all-platforms"></a>Alle Plattformen  
**Syntax**  
  
```  
__identifier(  
Visual_C++_keyword  
)  
  
```  
  
**Hinweise**  
  
Verwenden der `__identifier` Schlüsselwort für Bezeichner entsprechen, die keine Schlüsselwörter sind zulässig, jedoch als stilistischen dringend abgeraten.  
  
## <a name="windows-runtime"></a>Windows-Runtime  
  
### <a name="requirements"></a>Anforderungen  
 Compileroption: **/ZW**  
  
### <a name="examples"></a>Beispiele  
 **Beispiel**  
  
 Im folgenden Beispiel eine Klasse mit dem Namen `template` in c# erstellt und als DLL verteilt wird. In der Visual C++-Programm, verwendet der `template` -Klasse, die `__identifier` Schlüsselwort verbirgt die Tatsache, `template` ist ein standard C++-Schlüsselwort.  
  
```  
// identifier_template.cs  
// compile with: /target:library  
public class template {  
   public void Run() { }  
}  
```  
  
```  
// keyword__identifier.cpp  
// compile with: /ZW  
#using <identifier_template.dll>  
int main() {  
   __identifier(template)^ pTemplate = ref new __identifier(template)();  
   pTemplate->Run();  
}  
```  
  
## <a name="common-language-runtime"></a>Common Language Runtime 
 **Hinweise**  
  
 Die `__identifier` -Schlüsselwort ist gültig, wenn die **"/ CLR"** -Compileroption.  
  
### <a name="requirements"></a>Anforderungen  
 Compileroption: **/clr**  
  
### <a name="examples"></a>Beispiele  
 **Beispiel**  
  
 Im folgenden Beispiel eine Klasse mit dem Namen `template` in c# erstellt und als DLL verteilt wird. In der Visual C++-Programm, verwendet der `template` -Klasse, die `__identifier` Schlüsselwort verbirgt die Tatsache, `template` ist ein standard C++-Schlüsselwort.  
  
```  
// identifier_template.cs  
// compile with: /target:library  
public class template {  
   public void Run() { }  
}  
```  
  
```  
// keyword__identifier.cpp  
// compile with: /clr  
#using <identifier_template.dll>  
  
int main() {  
   __identifier(template) ^pTemplate = gcnew __identifier(template)();  
   pTemplate->Run();  
}  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Komponentenerweiterungen für Laufzeitplattformen](../windows/component-extensions-for-runtime-platforms.md)   
 [Komponentenerweiterungen für Laufzeitplattformen](../windows/component-extensions-for-runtime-platforms.md)