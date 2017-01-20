---
title: "Vererbung (C++)"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Klassen [C++], Abgeleitet"
  - "Abgeleitete Klassen"
  - "Abgeleitete Klassen, Informationen über abgeleitete Klassen"
ms.assetid: 3534ca19-d9ed-4a40-be1b-b921ad0e6956
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Vererbung (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

In diesem Abschnitt wird beschrieben, wie abgeleitete Klassen verwendet werden, um erweiterbare Programme zu erzeugen.  
  
## Überblick  
 Neue Klassen können aus vorhandenen Klassen mithilfe eines Mechanismus abgeleitet werden, der als "Vererbung" bezeichnet wird \(weitere Informationen finden Sie unter [Einfache Vererbung](../cpp/single-inheritance.md)\).  Klassen, die zur Ableitung verwendet werden, werden als "Basisklassen" einer bestimmten abgeleiteten Klasse bezeichnet.  Eine abgeleitete Klasse wird mit der folgenden Syntax deklariert:  
  
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
  
 Nach dem Tag für die Klasse wird ein Doppelpunkt gefolgt von einer Liste mit grundlegenden Spezifikationen angezeigt.  Die sogenannten Basisklassen müssen zuvor deklariert werden.  Die grundlegenden Spezifikationen können einen Zugriffsspezifizierer enthalten, der eines der Schlüsselwörter **public**, `protected` oder `private` ist.  Diese Zugriffsspezifizierer werden vor dem Basisklassennamen angezeigt und gelten nur für diese Basisklasse.  Diese Spezifizierer steuern die Berechtigung der abgeleiteten Klasse, die für Member der Basisklasse zu verwenden sind.  Weitere Informationen zum Zugriff auf Basisklassenmember finden Sie unter [Memberzugriffssteuerung](../cpp/member-access-control-cpp.md).  Wenn der Zugriffsspezifizierer weggelassen wird, wird der Zugriff dieser Basis als `private` betrachtet.  Die grundlegenden Spezifikationen können das Schlüsselwort **virtual** enthalten, um virtuelle Vererbung anzugeben.  Dieses Schlüsselwort kann vor oder nach dem Zugriffsspezifizierer angezeigt werden, falls vorhanden.  Wenn virtuelle Vererbung verwendet wird, wird die Basisklasse als virtuelle Basisklasse bezeichnet.  Weitere Informationen finden Sie unter [Virtuelle Basisklassen](../misc/virtual-base-classes.md).  
  
 Es können mehrere durch Kommas getrennte Basisklasse angegeben werden.  Wenn eine einzelne Basisklasse angegeben ist, handelt es sich um das Vererbungsmodell [Einfache Vererbung](../cpp/single-inheritance.md). Wenn mehrere Basisklassen angegeben sind, wird das Vererbungsmodell als [Mehrfachvererbung](assetId:///3b74185e-2beb-4e29-8684-441e51d2a2ca) bezeichnet.  
  
 Es sind folgende Themen enthalten:  
  
-   [Einfache Vererbung](../cpp/single-inheritance.md)  
  
-   [Mehrfachvererbung](assetId:///3b74185e-2beb-4e29-8684-441e51d2a2ca)  
  
-   [Mehrere Basisklassen](../cpp/multiple-base-classes.md)  
  
-   [Virtuelle Basisklassen](../misc/virtual-base-classes.md)  
  
-   [Virtuelle Funktionen](../cpp/virtual-functions.md)  
  
-   [Explizite Überschreibungen](../cpp/explicit-overrides-cpp.md)  
  
-   [Abstrakte Klassen](../cpp/abstract-classes-cpp.md)  
  
-   [Zusammenfassung der Bereichsregeln](../cpp/summary-of-scope-rules.md)  
  
 Die [\_\_super](../cpp/super.md)\- und [\_\_interface](../cpp/interface.md)\-Schlüsselwörter werden in diesem Abschnitt dokumentiert.  
  
## Siehe auch  
 [C\+\+\-Sprachreferenz](../cpp/cpp-language-reference.md)