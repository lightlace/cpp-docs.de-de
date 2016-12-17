---
title: "Implizites Boxing von Werttypen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__box-Schlüsselwort"
  - "Boxing"
  - "Boxing, __box-Schlüsselwort"
  - "Boxing, Visual C++"
  - "Werttypen, Geschachtelt"
ms.assetid: 9597c92f-a3fe-44af-ad80-f9d656847a35
caps.latest.revision: 9
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# Implizites Boxing von Werttypen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Das Boxing von Werttypen hat sich in [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)] gegenüber Managed Extensions for C\+\+ geändert.  
  
 Im Sprachdesign haben wir einen philosophischen Standpunkt über die praktische Erfahrung mit dem Feature gesetzt, was sich in der Praxis als Fehler erwiesen hat.  Analog entschied Stroustrup im ursprünglichen Mehrfachvererbungs\-Sprachdesign, dass ein Unterobjekt einer virtuellen Basisklasse nicht in einem abgeleiteten Klassenkonstruktor initialisiert werden kann. Daher verlangt die Sprache, dass jede Klasse, die als virtuelle Basisklasse dient, einen Standardkonstruktor definieren muss.  Es ist dieser Standardkonstruktor, der von jeder nachfolgenden virtuellen Ableitung aufgerufen wird.  
  
 Das Problem einer virtuellen Basisklassenhierarchie ist, dass sich die Verantwortung für die Initialisierung des freigegebenen virtuellen Unterobjekts mit jeder nachfolgenden Ableitung verschiebt.  Wenn ich beispielsweise eine Basisklasse definiere, für deren Initialisierung eine Pufferreservierung erforderlich ist, könnte die benutzerdefinierte Größe dieses Puffers als Argument an den Konstruktor übergeben werden.  Wenn ich nun zwei nachfolgende virtuelle Ableitungen bereitstelle, die ich `inputb` und `outputb` nenne, liefert jede von ihnen einen eigenen Wert an den Basisklassenkonstruktor.  Wenn ich außerdem eine `in_out`\-Klasse sowohl von `inputb` als auch von `outputb` ableite, kann keiner dieser an das gemeinsame Unterobjekt der virtuellen Basisklasse übergebenen Werte ausgewertet werden.  
  
 Deshalb gestattete Stroustrup im ursprünglichen Sprachdesign keine explizite Initialisierung der virtuellen Basisklasse innerhalb der Memberinitialisierungsliste des abgeleiteten Klassenkonstruktors.  Während dieses Problem zwar dadurch gelöst wurde, erwies sich die fehlende Möglichkeit, die Initialisierung der virtuellen Basisklasse zu steuern, jedoch als nicht praktikabel.  Keith Gorlen vom National Institute of Health, der eine Freewareversion der SmallTalk\-Auflistungsbibliothek mit dem Namen nihcl implementiert hatte, war nachhaltig daran beteiligt, Stroustrup zu überzeugen, ein flexibleres Sprachdesign zu entwickeln.  
  
 Es ist ein Prinzip objektorientierten hierarchischen Designs, dass eine abgeleitete Klasse sich nur auf die nicht\-privaten Implementierungen seiner unmittelbaren Basisklassen bezieht.  Um ein flexibles Initialisierungsdesign für virtuelle Vererbung zu unterstützen, musste Stroustrup gegen dieses Prinzip verstoßen.  Die am meisten abgeleitete Klasse in einer Hierarchie übernimmt die Verantwortung für alle Initialisierungen virtueller Unterobjekte, unabhängig davon, wie tief es in der Hierarchieebene liegt.  Z. B. sind `inputb` und `outputb` beide zuständig für das explizite Initialisieren ihrer unmittelbaren virtuellen Basisklasse.  Wenn `in_out` sowohl von `inputb` als auch von `outputb` abgeleitet ist, übernimmt `in_out` die Verantwortung für die Initialisierung der einmal beseitigten virtuellen Basisklasse, und die explizite Initialisierung innerhalb von `inputb` und `outputb` wird unterdrückt.  
  
 Dies stellt die von Sprachentwicklern geforderte Flexibilität bereit, jedoch um den Preis einer komplizierten Semantik.  Diese Last der Komplikation wird beseitigt, wenn wir festlegen, dass eine virtuelle Basisklasse zustandslos ist und sie nur eine Schnittstelle angeben darf.  Dies ist innerhalb von C\+\+ ein empfohlenes Designidiom.  Innerhalb der CLR\-Programmierung ist es mit dem Schnittstellentyp zur Richtlinie erhoben worden.  
  
 Es folgt ein einfaches Codebeispiel, bei dem explizites Boxing unnötig ist:  
  
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
  
 Wie Sie sehen können, findet dort eine ganze Menge Boxing statt.  In [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)] ist Werttypboxing implizit:  
  
```  
// new syntax makes boxing implicit  
array<int>^ my1DIntArray = {1,2,3,4,5};  
array<Object^>^ myObjArray = {26,27,28,29,30};  
  
Console::WriteLine( "{0}\t{1}\t{2}", 0,   
   my1DIntArray->GetLowerBound( 0 ),   
   my1DIntArray->GetUpperBound( 0 ) );  
```  
  
## Siehe auch  
 [Werttypen und ihr Verhalten \(C\+\+\/CLI\)](../dotnet/value-types-and-their-behaviors-cpp-cli.md)   
 [Boxing](../windows/boxing-cpp-component-extensions.md)