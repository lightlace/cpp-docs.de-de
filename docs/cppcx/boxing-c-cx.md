---
title: Boxing (C++ / CX) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: language-reference
ms.assetid: edfb12fa-2a9b-42f6-bdac-d4d76cb8274e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8ed67496189388b869d7d9491ac4baad3de810ca
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2018
ms.locfileid: "43203591"
---
# <a name="boxing-ccx"></a>Boxing (C++/CX)
*Boxing* wird eine Werttypvariable wie z. B. wrapping [Windows::Foundation::DateTime](https://msdn.microsoft.com/library/windows/apps/windows.foundation.datetime.aspx)– oder ein grundlegender Skalartyp wie z. B. `int`– in einer Verweisklasse, wenn die Variable an eine Methode übergeben wird, die akzeptiert [ Platform:: Object ^](../cppcx/platform-object-class.md) als Eingabetyp.  
  
## <a name="passing-a-value-type-to-an-object-parameter"></a>Übergeben eines Werttyps an einen Object^-Parameter  
 Obwohl Sie für eine Variable nicht explizit Boxing anwenden müssen, um sie an einen Methodenparameter des Typs [Platform::Object^](../cppcx/platform-object-class.md)zu übergeben, müssen Sie eine Umwandlung zum ursprünglichen Typ explizit vornehmen, wenn Sie Werte abrufen, die zuvor geschachtelt wurden.  
  
 [!code-cpp[cx_boxing#01](../cppcx/codesnippet/CPP/cx_boxing/class1.cpp#01)]  
  
### <a name="using-platformiboxt-to-support-nullable-value-types"></a>Verwenden von Platform:: ibox\<T > zur Unterstützung von auf NULL festlegbare Werttypen  
 C# und Visual Basic unterstützen das Konzept von Typen, die NULL-Werte zulassen. In C++ / CX können Sie die `Platform::IBox<T>` Typ um öffentliche Methoden verfügbar zu machen, die Werttypparameter unterstützen. Das folgende Beispiel zeigt C++ / CX-öffentliche Methode, die null zurückgibt, wenn ein C#-Aufrufer für eines der Argumente null übergibt.  
  
 [!code-cpp[cx_boxing#02](../cppcx/codesnippet/CPP/cx_boxing/class1.h#02)]  
  
 In einem C#-XAML-Client können Sie diese Methode wie folgt verwenden:  
  
```  
  
// C# client code  
    BoxingDemo.Class1 obj = new BoxingDemo.Class1();  
    int? a = null;  
    int? b = 5;  
    var result = obj.Multiply(a,b); //result = null  
  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Typsystem (C++/CX)](../cppcx/type-system-c-cx.md)   
 [Umwandlung (C++ / CX)](../cppcx/casting-c-cx.md)   
 [Sprachreferenz zu Visual C++](../cppcx/visual-c-language-reference-c-cx.md)   
 [Namespaceverweis](../cppcx/namespaces-reference-c-cx.md)