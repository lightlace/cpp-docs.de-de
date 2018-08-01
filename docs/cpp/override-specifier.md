---
title: override-Bezeichner | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- override Identifier
ms.assetid: b286fb46-9374-4ad8-b2e7-4607119b6133
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c95a67df03f62279b7b9c46ef41b6cafe7ff3df1
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/01/2018
ms.locfileid: "39408150"
---
# <a name="override-specifier"></a>override-Bezeichner
Sie können die **außer Kraft setzen** Schlüsselwort, um Memberfunktionen festzulegen, die eine virtuelle Funktion in einer Basisklasse überschreiben.  
  
## <a name="syntax"></a>Syntax  
  
```  
function-declaration override;  
```  
  
## <a name="remarks"></a>Hinweise  
 **außer Kraft setzen** ist kontextbezogen und hat eine besondere Bedeutung, wenn sie nach einer memberfunktionsdeklaration verwendet wird; andernfalls wird Sie kein reserviertes Schlüsselwort.  
  
## <a name="example"></a>Beispiel  
 Verwendung **überschreiben** um Vererbungsverhalten im Code zu verhindern. Das folgende Beispiel zeigt, wo, ohne **überschreiben**, das memberfunktionsverhalten der abgeleiteten Klasse möglicherweise nicht vorgesehen wurde. Der Compiler gibt keinen Fehler für diesen Code aus.  
  
```cpp  
class BaseClass  
{  
    virtual void funcA();  
    virtual void funcB() const;  
    virtual void funcC(int = 0);  
    void funcD();  
};  
  
class DerivedClass: public BaseClass  
{  
    virtual void funcA(); // ok, works as intended  
  
    virtual void funcB(); // DerivedClass::funcB() is non-const, so it does not  
                          // override BaseClass::funcB() const and it is a new member function  
  
    virtual void funcC(double = 0.0); // DerivedClass::funcC(double) has a different  
                                      // parameter type than BaseClass::funcC(int), so  
                                      // DerivedClass::funcC(double) is a new member function  
};  
```  
  
 Bei Verwendung von **überschreiben**, generiert der Compiler Fehler, anstatt im Hintergrund Erstellen von neuen Member-Funktionen.  
  
```cpp  
class BaseClass  
{  
    virtual void funcA();  
    virtual void funcB() const;  
    virtual void funcC(int = 0);  
    void funcD();  
};  
  
class DerivedClass: public BaseClass  
{  
    virtual void funcA() override; // ok  
  
    virtual void funcB() override; // compiler error: DerivedClass::funcB() does not   
                                   // override BaseClass::funcB() const  
  
    virtual void funcC( double = 0.0 ) override; // compiler error:   
                                                 // DerivedClass::funcC(double) does not   
                                                 // override BaseClass::funcC(int)  
  
    void funcD() override; // compiler error: DerivedClass::funcD() does not   
                           // override the non-virtual BaseClass::funcD()  
};  
```  
  
 Um anzugeben, dass Funktionen nicht überschrieben werden können und Klassen nicht geerbt werden können, verwenden die [endgültige](../cpp/final-specifier.md) Schlüsselwort.  
  
## <a name="see-also"></a>Siehe auch  
 [final-Bezeichner](../cpp/final-specifier.md)   
 [Schlüsselwörter](../cpp/keywords-cpp.md)   