---
title: außer Kraft setzen (Komponentenerweiterungen für C++) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- overriding, override keyword [C++]
- override keyword [C++]
ms.assetid: 34d19257-1686-4fcd-96f5-af07c70ba914
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6818256aafc64702e5423a5560c251e6d46750fa
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
ms.locfileid: "33878878"
---
# <a name="override--c-component-extensions"></a>override (Komponentenerweiterungen für C++)
Das kontextbezogene `override`-Schlüsselwort gibt an, dass ein Member eines Typs eine Basisklasse oder einen Basisschnittstellenmember überschreibt.  
  
## <a name="remarks"></a>Hinweise  
 Die `override` Schlüsselwort ist gültig, beim Kompilieren für systemeigene Ziele (standardmäßige Compileroption), Windows-Runtime-Ziele (**/Zw** -Compileroption), oder der common Language Runtime-Ziele (**"/ CLR"** Compiler (Option).  
  
 Weitere Informationen zu überschreibungsspezifizierern finden Sie unter [Überschreibungsspezifizierer](../cpp/override-specifier.md) und [Überschreibungsspezifizierer und Native Kompilierungen](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md).  
  
 Weitere Informationen zu kontextbezogenen Schlüsselwörtern finden Sie unter [Kontextbezogene Schlüsselwörter](../windows/context-sensitive-keywords-cpp-component-extensions.md).  
  
## <a name="examples"></a>Beispiele  
 **Beispiel**  
  
 Das folgende Codebeispiel zeigt, dass `override` auch in systemeigenen Kompilierungen verwendet werden kann.  
  
```cpp#  
// override_keyword_1.cpp  
// compile with: /c  
struct I1 {  
   virtual void f();  
};  
  
struct X : public I1 {  
   virtual void f() override {}  
};  
```  
  
 **Beispiel**  
  
 Das folgende Codebeispiel zeigt, dass `override` auch in Windows-Runtime-Kompilierungen verwendet werden kann.  
  
```cpp#  
// override_keyword_2.cpp  
// compile with: /ZW /c  
ref struct I1 {  
   virtual void f();  
};  
  
ref struct X : public I1 {  
   virtual void f() override {}  
};  
```  
  
 **Anforderungen**  
  
 Compileroption: **/ZW**  
  
 **Beispiel**  
  
 Das folgende Codebeispiel zeigt, dass `override` auch in Common Language Runtime-Kompilierungen verwendet werden kann.  
  
```cpp#  
// override_keyword_3.cpp  
// compile with: /clr /c  
ref struct I1 {  
   virtual void f();  
};  
  
ref struct X : public I1 {  
   virtual void f() override {}  
};  
```  
  
 **Anforderungen**  
  
 Compileroption: **/clr**  
  
## <a name="see-also"></a>Siehe auch  
 [Überschreibungsspezifizierer](../cpp/override-specifier.md)   
 [Überschreibungsspezifizierer](../windows/override-specifiers-cpp-component-extensions.md)