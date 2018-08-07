---
title: __identifier (C++ / CLI) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- __identifier
- __identifier_cpp
dev_langs:
- C++
helpviewer_keywords:
- __identifier keyword [C++]
ms.assetid: 348428af-afa7-4ff3-b571-acf874301cf2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6eac892da91c5f3640bdd243a0b3c6525faa5c2a
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/07/2018
ms.locfileid: "39603344"
---
# <a name="identifier-ccli"></a>__identifier (C++/CLI)
Ermöglicht die Verwendung von Visual C++-Schlüsselwörter als Bezeichner.  
  
## <a name="all-platforms"></a>Alle Plattformen  
### <a name="syntax"></a>Syntax  
  
```  
__identifier(  
Visual_C++_keyword  
)  
```  
  
### <a name="remarks"></a>Hinweise  
  
Verwenden der **__identifier** Schlüsselwort für Bezeichner entsprechen, die keine Schlüsselwörter sind zulässig, jedoch nicht empfohlen, als eine Frage des Stils.  
  
## <a name="windows-runtime"></a>Windows-Runtime  
  
### <a name="requirements"></a>Anforderungen  
 Compileroption: `/ZW`  
  
### <a name="examples"></a>Beispiele  
 **Beispiel**  
  
 Im folgenden Beispiel wird eine Klasse namens `template` in c# erstellt wurde und als eine DLL-Datei verteilt wird. In der Visual C++-Programm, das verwendet die `template` -Klasse, die **__identifier** Schlüsselwort verbirgt die Tatsache, **Vorlage** ist ein standard C++-Schlüsselwort.  
  
```cs  
// identifier_template.cs  
// compile with: /target:library  
public class template {  
   public void Run() { }  
}  
```  
  
```cpp  
// keyword__identifier.cpp  
// compile with: /ZW  
#using <identifier_template.dll>  
int main() {  
   __identifier(template)^ pTemplate = ref new __identifier(template)();  
   pTemplate->Run();  
}  
```  
  
## <a name="common-language-runtime"></a>Common Language Runtime 
### <a name="remarks"></a>Hinweise  
  
 Die **__identifier** Schlüsselwort ist gültig, mit der `/clr` -Compileroption.  
  
### <a name="requirements"></a>Anforderungen  
 Compileroption: `/clr`  
  
### <a name="examples"></a>Beispiele  
  
 Im folgenden Beispiel wird eine Klasse namens `template` in c# erstellt wurde und als eine DLL-Datei verteilt wird. In der Visual C++-Programm, das verwendet die `template` -Klasse, die **__identifier** Schlüsselwort verbirgt die Tatsache, **Vorlage** ist ein standard C++-Schlüsselwort.  
  
```cs  
// identifier_template.cs  
// compile with: /target:library  
public class template {  
   public void Run() { }  
}  
```  
  
```cpp  
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