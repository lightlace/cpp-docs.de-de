---
title: Änderungen in der Initialisierungsreihenfolge für Konstruktoren | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- constructors, C++
ms.assetid: 8892c38d-6bf7-4cf7-ac8f-15e052135a79
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 32dad73e3d2026726e3042b0c619eeff11a5f57c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="changes-in-constructor-initialization-order"></a>Änderungen in der Initialisierungsreihenfolge für Konstruktoren
Die Reihenfolge der Initialisierung für Klassenkonstruktoren wurde von Managed Extensions für C++ in Visual C++ geändert.  
  
## <a name="comparison-of-constructor-initialization-order"></a>Vergleich der Initialisierungsreihenfolge für Konstruktoren  
 In Managed Extensions für C++ Konstruktorinitialisierung, die in der folgenden Reihenfolge ist aufgetreten:  
  
1.  Der Konstruktor der Basisklasse, wird ggf. aufgerufen.  
  
2.  Die Initialisierungsliste der Klasse wird ausgewertet.  
  
3.  Der Codetext der Klassenkonstruktor wird ausgeführt.  
  
 Diese Reihenfolge der Ausführung folgt die gleichen Konventionen wie systemeigene C++-Programmierung. Die neue Visual C++-Sprache gibt die folgenden Ausführungsreihenfolge für CLR-Klassen vor:  
  
1.  Die Initialisierungsliste der Klasse wird ausgewertet.  
  
2.  Der Konstruktor der Basisklasse, wird ggf. aufgerufen.  
  
3.  Der Codetext der Klassenkonstruktor wird ausgeführt.  
  
 Beachten Sie, dass diese Änderung nur für CLR-Klassen gilt. systemeigene Klassen in Visual C++ folgen weiterhin früheren Konventionen. In beiden Fällen kaskadiert werden diese Regeln nach oben in der Kette gesamte Hierarchie einer angegebenen Klasse.  
  
 Beachten Sie im folgenden Codebeispiel wird die Verwendung von Managed Extensions for C++:  
  
```  
__gc class A  
{  
public:  
   A() : _n(1)  
   {  
   }  
  
protected:  
   int _n;  
};  
  
__gc class B : public A  
{  
public:  
   B() : _m(_n)  
   {  
   }  
private:  
   int _m;  
};  
```  
  
 Nach der Initialisierungsreihenfolge für Konstruktoren oben vorgeschrieben, sehen wir die folgende Reihenfolge der Ausführung, wenn neue Instanzen der Klasse `B` erstellt werden:  
  
1.  Der Konstruktor der Basisklasse `A` aufgerufen wird. Die `_n` Member wird initialisiert, um `1`.  
  
2.  Der Initialisierungsliste für Klasse `B` ausgewertet wird. Die `_m` Member wird initialisiert, um `1`.  
  
3.  Der Codetext "der Klasse `B` ausgeführt wird.  
  
 Nun sehen wir uns mit den gleichen Code in der neuen Visual C++-Syntax:  
  
```  
ref class A  
{  
public:  
   A() : _n(1)  
   {  
   }  
  
protected:  
   int _n;  
};  
  
ref class B : A  
{  
public:  
   B() : _m(_n)  
   {  
   }  
private:  
   int _m;  
};  
```  
  
 Die Reihenfolge der Ausführung, wenn neue Instanzen der Klasse `B` erstellt werden, unter der neuen Syntax lautet:  
  
1.  Der Initialisierungsliste für Klasse `B` ausgewertet wird. Die `_m` Member wird initialisiert, um `0` (`0` ist der Wert nicht initialisierte, der die `_m` Klassenmember).  
  
2.  Der Konstruktor der Basisklasse `A` aufgerufen wird. Die `_n` Member wird initialisiert, um `1`.  
  
3.  Der Codetext "der Klasse `B` ausgeführt wird.  
  
 Beachten Sie, dass eine ähnliche Syntax für diese Codebeispiele unterschiedliche Ergebnisse erzeugt. Der Konstruktor der Klasse `B` richtet sich nach einem Wert von der Basisklasse `A` zum Initialisieren des Elements. Allerdings der Konstruktor für die Klasse `A` noch nicht aufgerufen. Diese Abhängigkeit kann besonders gefährlich sein, wenn eine Speicher- oder Zuweisung im Konstruktor Basisklasse die geerbte Klasse abhängig ist.  
  
## <a name="what-this-means-going-from-managed-extensions-for-c-to-visual-c-2010"></a>Was dies bedeutet, die für den Wechsel von Managed Extensions for C++ auf Visual C++ 2010  
 In vielen Fällen sollte die Änderungen an die Ausführungsreihenfolge der Klassenkonstruktoren für den Programmierer transparent sein, da Basisklassen nicht notwendig, das Verhalten des geerbten Klassen aufweisen. Jedoch, wie diese Codebeispiele veranschaulichen zu können, können die Konstruktoren des geerbten Klassen erheblich beeinträchtigt werden bei ihrer Initialisierungslisten von den Werten der Basisklassenmember abhängen. Wenn Sie den Code von Managed Extensions für C++ in der neuen Syntax verschieben, erwägen Sie, solche Konstrukte in den Text der Konstruktor der Klasse, in dem die Ausführung garantiert wird, zuletzt ausgeführt.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwaltete Typen (C + c++ / CL)](../dotnet/managed-types-cpp-cl.md)   
 [Konstruktoren](../cpp/constructors-cpp.md)   
 