---
title: Private virtuelle Funktionen | Microsoft Docs
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
- virtual functions, private
- derived classes, virtual functions
- access modifiers [C++], for class members
- member access [C++], virtual members
ms.assetid: 04448086-bf72-44be-9c1f-dfda1744949e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 9b407bc469a345706f99cf5bad578f678e652a4c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="private-virtual-functions"></a>Private virtuelle Funktionen
Private virtuelle Funktionen in abgeleiteten Klassen behandelt werden wie wurde von Managed Extensions für C++ in Visual C++ geändert.  
  
 In Managed Extensions schränkt die Zugriffsebene einer virtuellen Funktion nicht die Möglichkeit, die in einer abgeleiteten Klasse außer Kraft gesetzt werden. In der neuen Syntax kann keine virtuelle Funktion eine virtuelle Funktion der Basisklasse überschreiben, die nicht zugegriffen werden kann. Zum Beispiel:  
  
```  
__gc class MyBaseClass {  
   // inaccessible to a derived class   
   virtual void g();  
};  
  
__gc class MyDerivedClass : public MyBaseClass {  
public:  
   // okay in Managed Extensions; g() overrides MyBaseClass::g()  
   // error in new syntax; cannot override: MyBaseClass::g() is inaccessible  
   void g();  
};  
```  
  
 Es gibt keine echte Zuordnung dieser Art von Design auf die neue Syntax. Eine verfügt über einfach auf die Member der Basisklasse zugegriffen werden kann – d. h. nicht privaten. Die geerbten Methoden müssen nicht den gleichen Zugriff tragen. In diesem Beispiel wird die Änderung am wenigsten eindringt an, um die MyBaseClass Element `protected`. Auf diese Weise wird die allgemeine Anwendung Zugriff auf die Methode über MyBaseClass noch nicht zulässig.  
  
```  
ref class MyBaseClass {  
protected:  
   virtual void g();  
};  
  
ref class MyDerivedClass : MyBaseClass {  
public:  
   virtual void g() override;  
};  
```  
  
 Beachten Sie, dass das Fehlen der expliziten `virtual` Schlüsselwort in der Basisklasse in der neuen Syntax wird eine Warnmeldung generiert.  
  
## <a name="see-also"></a>Siehe auch  
 [Memberdeklarationen innerhalb einer Klasse oder Schnittstelle (C++/CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)   
 