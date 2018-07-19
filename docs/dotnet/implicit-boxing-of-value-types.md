---
title: Implizites Boxing von Werttypen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- boxing, Visual C++
- __box keyword
- boxing
- boxing, __box keyword
- value types, boxed
ms.assetid: 9597c92f-a3fe-44af-ad80-f9d656847a35
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: f1f5a455333e5cb40b63d5a5237b2df053cef194
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33132218"
---
# <a name="implicit-boxing-of-value-types"></a>Implizites Boxing von Werttypen
Das Boxing von Werttypen wurde von Managed Extensions für C++ in Visual C++ geändert.  
  
 Im Language-Entwurf wir eine philosophischen Position praktische Erfahrung mit dem Feature eingeführt, und in der Praxis, die es wurde ein Fehler unterläuft. Als eine Analogie hierzu beschlossen in der ursprünglichen mehrere Vererbung Language Design Stroustrup, dass eine virtuelle Basisklasse Unterobjekt nicht innerhalb der Konstruktor einer abgeleiteten Klasse initialisiert werden konnte, und daher die Sprache erforderlich, die jede Klasse dient als virtuelle Basisklasse Klasse muss einen Standardkonstruktor definiert werden. Es ist dieser Standardkonstruktor, der von jeder nachfolgenden virtuellen Ableitung aufgerufen wird.  
  
 Das Problem einer Hierarchie für die virtuelle Basisklasse ist, dass die Verantwortung für die Initialisierung der freigegebenen virtuellen Unterobjekts mit jeder nachfolgenden Ableitung verschiebt. Angenommen, wenn ich eine Basisklasse für definieren die Initialisierung die Zuweisung eines Puffers, der vom Benutzer angegebenen Größe für diesen Puffer erfordert möglicherweise als Argument an den Konstruktor übergeben werden. Wenn ich dann zwei nachfolgende virtuelle ableitungen bereitstellen, anrufen `inputb` und `outputb`, jeweils einen bestimmten Wert an den Konstruktor der Basisklasse enthält. Wenn ich jetzt abgeleitete ein `in_out` Klasse sowohl `inputb` und `outputb`, keiner dieser Werte auf das freigegebene virtuelle Basisklasse Unterobjekt darf auf angemessene Weise ausgewertet.  
  
 Aus diesem Grund nicht Stroustrup des ursprünglichen Entwurfs für die Sprache einer virtuellen Basisklasse innerhalb der Member-Initialisierungsliste des Konstruktors abgeleiteten Klasse die explizite Initialisierung zulässig. Während dies bei der Behebung des Problems nachgewiesen die Unfähigkeit in Bezug auf die Initialisierung der virtuellen Basisklasse direkt in der Praxis nicht praktikabel. Keith Gorlen war vom National Institute of Health, der eine freewarehilfsprogramm-Version der SmallTalk Auflistung Bibliothek aufgerufen Nihcl implementiert hatte, eine Stimme Prinzip Stroustrup, die er musste ein flexibler Language Design zu überzeugen.  
  
 Ein Prinzip der objektorientierten hierarchische Entwurf enthält, eine abgeleitete Klasse nur mit der Implementierung nicht privaten sofortigen Basisklassen betreffen werden sollte. Um einen flexiblen Initialisierung Entwurf für die virtuelle Vererbung unterstützen, musste Stroustrup dieses Prinzip verstoßen. Die am stärksten abgeleitete Klasse in einer Hierarchie Verantwortung für alle virtuellen Unterobjekt Initialisierung unabhängig davon, wie tief in der Hierarchie, wenn er vorkommt. Beispielsweise `inputb` und `outputb` sind zuständig für das explizite initialisieren ihrer unmittelbaren virtuellen Basisklasse. Wenn `in_out` ableitet, beide `inputb` und `outputb`, `in_out` ist verantwortlich für die Initialisierung der einmal virtuelle Basisklasse entfernt und die Initialisierung innerhalb expliziter vorgenommen `inputb` und `outputb` ist unterdrückt.  
  
 Dies bietet die Flexibilität, die von Sprachenentwicklern, jedoch auch zu einer komplizierten Semantik erforderlich. Diese Last der Komplikation wird sofort entfernt werden, wenn wir eine virtuelle Basisklasse zustandslos ist und einfach an eine Schnittstelle einschränken. Dies ist eine empfohlene Vorgehensweise in C++. In CLR-Programmierung wird diese Richtlinie mit dem Schnittstellentyp ausgelöst.  
  
 Hier ist eine einfache Code-Beispiel - und explizite Boxing ist in diesem Fall nicht erforderlich:  
  
```  
// Managed Extensions for C++ requires explicit __box operation  
int my1DIntArray __gc[] = { 1, 2, 3, 4, 5 };  
Object* myObjArray __gc[] = {   
   __box(26), __box(27), __box(28), __box(29), __box(30)  
};  
  
Console::WriteLine( "{0}\t{1}\t{2}", __box(0),  
   __box(my1DIntArray->GetLowerBound(0)),  
   __box(my1DIntArray->GetUpperBound(0)) );  
```  
  
 Wie Sie sehen können, ist es viel Boxing statt. Unter Visual C++-Werttyp Boxing ist implizit:  
  
```  
// new syntax makes boxing implicit  
array<int>^ my1DIntArray = {1,2,3,4,5};  
array<Object^>^ myObjArray = {26,27,28,29,30};  
  
Console::WriteLine( "{0}\t{1}\t{2}", 0,   
   my1DIntArray->GetLowerBound( 0 ),   
   my1DIntArray->GetUpperBound( 0 ) );  
```  
  
## <a name="see-also"></a>Siehe auch  
 [Werttypen und ihr Verhalten (C + c++ / CLI)](../dotnet/value-types-and-their-behaviors-cpp-cli.md)   
 [Boxing](../windows/boxing-cpp-component-extensions.md)