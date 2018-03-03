---
title: Versiegeln einer virtuellen Funktion | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- sealed keyword [C++]
- derived classes, virtual functions
- virtual functions, sealing
- __sealed keyword
ms.assetid: 0e9fae03-6425-4512-9a24-8ccb6dc8a0d4
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 48d52a2697289197555438847ba2fcb86aeb3235
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="sealing-a-virtual-function"></a>Versiegeln einer virtuellen Funktion
Die Syntax für das Versiegeln einer virtuellen Funktion hat gegenüber Managed Extensions für C++ in Visual C++ geändert.  
  
 Die `__sealed` -Schlüsselwort wird in Managed Extensions verwendet, so ändern Sie entweder einen Verweistyp, nachfolgende Ableitung von untersagen (finden Sie unter [Deklaration eines verwalteten Klassentyps](../dotnet/declaration-of-a-managed-class-type.md)), oder ändern eine virtuelle Funktion untersagen nachfolgende Überschreiben der Methode in einer abgeleiteten Klasse. Zum Beispiel:  
  
```  
__gc class base { public: virtual void f(); };  
__gc class derived : public base {  
public:  
   __sealed void f();  
};  
```  
  
 In diesem Beispiel `derived::f()` überschreibt die `base::f()` -Instanz basierend auf die genaue Übereinstimmung der Funktionsprototypen. Die `__sealed` -Schlüsselwort Gibt an, dass es sich bei eine nachfolgenden Klasse geerbt von der abgeleiteten Klasse eine Überschreibung der bereitstellen kann `derived::f()`.  
  
 In der neuen Syntax `sealed` wird nach der Signatur, statt an einer beliebigen Stelle vor dem tatsächlichen Funktionsprototyp angezeigt werden, wie bisher erlaubten zulässiger platziert. Darüber hinaus die Verwendung von `sealed` verlangt eine ausdrückliche Verwendung von der `virtual` -Schlüsselworts. D. h. die ordnungsgemäße Übersetzung von `derived`oben lautet wie folgt:  
  
```  
ref class derived: public base {  
public:  
   virtual void f() override sealed;  
};  
```  
  
 Das Fehlen der `virtual` Schlüsselwort in dieser Instanz führt zu einem Fehler. In der neuen Syntax wird das kontextbezogene Schlüsselwort `abstract` kann verwendet werden, anstelle von der `=0` um eine rein virtuelle Funktion anzugeben. Diese Möglichkeit wurde in Managed Extensions nicht unterstützt. Zum Beispiel:  
  
```  
__gc class base { public: virtual void f()=0; };  
```  
  
 kann als umgeschrieben werden  
  
```  
ref class base { public: virtual void f() abstract; };  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Memberdeklarationen innerhalb einer Klasse oder Schnittstelle (C + c++ / CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)   
 [sealed](../windows/sealed-cpp-component-extensions.md)