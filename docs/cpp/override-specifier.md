---
title: Überschreibungsspezifizierer | Microsoft Docs
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
ms.openlocfilehash: 4d43620ceeb0404c3ad8b10cee3d0a00e7b2f467
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="override-specifier"></a>override-Bezeichner
Sie können das Schlüsselwort `override` verwenden, um Memberfunktionen festzulegen, die eine virtuelle Funktion in einer Basisklasse überschreiben.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
function-declaration override;  
```  
  
## <a name="remarks"></a>Hinweise  
 `override` ist kontextbezogen und hat eine besondere Bedeutung, wenn es nach der Deklaration einer Memberfunktion verwendet wird; andernfalls ist es kein reserviertes Schlüsselwort.  
  
## <a name="example"></a>Beispiel  
 Verwenden Sie `override`, um unbeabsichtigtes Vererbungsverhalten im Code zu verhindern. Das folgende Beispiel zeigt, ohne `override`, wo das Memberfunktionsverhalten der abgeleiteten Klasse möglicherweise nicht vorgesehen wurde. Der Compiler gibt keinen Fehler für diesen Code aus.  
  
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
  
 Wenn Sie `override` verwenden, generiert der Compiler Fehler, anstatt neue Memberfunktionen automatisch zu erstellen.  
  
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
  
 Verwenden, um anzugeben, dass Funktionen nicht überschrieben werden können und Klassen geerbt werden können, die [endgültigen](../cpp/final-specifier.md) Schlüsselwort.  
  
## <a name="see-also"></a>Siehe auch  
 [final-Bezeichner](../cpp/final-specifier.md)   
 [Schlüsselwörter](../cpp/keywords-cpp.md)   
 