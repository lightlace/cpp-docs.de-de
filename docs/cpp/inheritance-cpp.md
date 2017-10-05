---
title: Vererbung (C++) | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- derived classes
- derived classes, about derived classes
- classes [C++], derived
ms.assetid: 3534ca19-d9ed-4a40-be1b-b921ad0e6956
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: dba45acbc602465db876038e83cb0cd496b2337e
ms.contentlocale: de-de
ms.lasthandoff: 09/25/2017

---
# <a name="inheritance--c"></a>Vererbung  (C++)
In diesem Abschnitt wird beschrieben, wie abgeleitete Klassen verwendet werden, um erweiterbare Programme zu erzeugen.  
  
## <a name="overview"></a>Übersicht  
 Neue Klassen aus vorhandenen Klassen, die mit einem Mechanismus namens "Vererbung" abgeleitet werden können (siehe die Informationen ab [einfache Vererbung](../cpp/single-inheritance.md)). Klassen, die zur Ableitung verwendet werden, werden als "Basisklassen" einer bestimmten abgeleiteten Klasse bezeichnet. Eine abgeleitete Klasse wird mit der folgenden Syntax deklariert:  
  
```  
 class Derived : [virtual] [access-specifier] Base  
{  
   // member list  
};  
 class Derived : [virtual] [access-specifier] Base1,  
 [virtual] [access-specifier] Base2, . . .  
{  
   // member list  
};  
```  
  
 Nach dem Tag für die Klasse wird ein Doppelpunkt gefolgt von einer Liste mit grundlegenden Spezifikationen angezeigt.  Die sogenannten Basisklassen müssen zuvor deklariert werden.  Die grundlegenden Spezifikationen können einen Zugriffsspezifizierer, die eines der Schlüsselwörter ist enthalten **öffentlichen**, `protected` oder `private`.  Diese Zugriffsspezifizierer werden vor dem Basisklassennamen angezeigt und gelten nur für diese Basisklasse.  Diese Spezifizierer steuern die Berechtigung der abgeleiteten Klasse, die für Member der Basisklasse zu verwenden sind.  Finden Sie unter [Memberzugriffssteuerung](../cpp/member-access-control-cpp.md) Informationen für den Zugriff auf Basisklassenmember.  Wenn der Zugriffsspezifizierer weggelassen wird, wird der Zugriff dieser Basis als `private` betrachtet.  Die grundlegenden Spezifikationen möglicherweise enthalten das Schlüsselwort **virtuellen** um virtuelle Vererbung anzugeben.  Dieses Schlüsselwort kann vor oder nach dem Zugriffsspezifizierer angezeigt werden, falls vorhanden.  Wenn virtuelle Vererbung verwendet wird, wird die Basisklasse als virtuelle Basisklasse bezeichnet.  
  
 Es können mehrere durch Kommas getrennte Basisklasse angegeben werden.  Wenn eine einzelne Basisklasse angegeben ist, wird das Vererbungsmodell [einzelne Vererbung](../cpp/single-inheritance.md). Wenn mehr als einer Basisklasse angegeben ist, heißt das Vererbungsmodell [mehrfachvererbung](http://msdn.microsoft.com/en-us/3b74185e-2beb-4e29-8684-441e51d2a2ca),  
  
 Es sind folgende Themen enthalten:  
  
-   [Einfache Vererbung](../cpp/single-inheritance.md)  
  
-   [Mehrfache Vererbung](http://msdn.microsoft.com/en-us/3b74185e-2beb-4e29-8684-441e51d2a2ca)  
  
-   [Mehrere Basisklassen](../cpp/multiple-base-classes.md)  
  
-   [Virtuelle Funktionen](../cpp/virtual-functions.md)  
  
-   [Explizite überschreibungen](../cpp/explicit-overrides-cpp.md)  
  
-   [Abstrakte Klassen](../cpp/abstract-classes-cpp.md)  
  
-   [Zusammenfassung der Bereichsregeln](../cpp/summary-of-scope-rules.md)  
  
 Die [__super](../cpp/super.md) und [__interface](../cpp/interface.md) Schlüsselwörter sind in diesem Abschnitt dokumentiert.  
  
## <a name="see-also"></a>Siehe auch  
 [C++-Programmiersprachenreferenz](../cpp/cpp-language-reference.md)
