---
title: "Basic Mechanics of Attributes"
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
  - "attributes [C++], inserting in code"
  - "attributes [C++], about attributes"
ms.assetid: dc2069c3-b9f3-4a72-965c-4e5208ce8e34
caps.latest.revision: 7
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Basic Mechanics of Attributes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Es gibt drei Möglichkeiten, um Attribute in das Projekt eingefügt.  Erstens können Sie sie manuell im Quellcode einfügen.  Zweitens können Sie sie mithilfe des Eigenschaftenrasters eines Objekts im Projekt einfügen.  Schließlich können Sie sie mithilfe der verschiedenen Assistenten einfügen.  Weitere Informationen zum Verwenden des Eigenschaftenfensters und der verschiedenen Assistenten finden Sie unter [Erstellen und Verwalten von Visual C\+\+\-Projekten](../ide/creating-and-managing-visual-cpp-projects.md).  
  
 Ab Visual C\+\+ .NET, erkennt der Compiler das Vorhandensein von Attributen in einer Quelldatei und ist in der Lage, diese während der Kompilierung dynamisch zu analysieren und zu untersuchen.  
  
 Wie, bevor, wenn das Projekt erstellt wird, der Compiler eine C\+\+\-Quelldatei analysiert, eine Objektdatei erzeugend.  Wenn der Compiler ein Attribut trifft, wird sie analysiert und validiert syntaktisch.  Der Compiler ruft dann dynamisch Attribut einen Anbieter an, um den Code einzufügen oder andere Änderungen zur Kompilierzeit ausführen.  Die Implementierung des Anbieters unterscheidet sich nach dem Typ des Attributs.  Beispielsweise werden durch Attribute ATL\-verknüpfte Atlprov.dll implementiert.  
  
 In der folgenden Abbildung wird die Beziehung zwischen dem Attribut und dem Compiler.  
  
 ![Komponentenattributkommunikation](../windows/media/vccompattrcomm.png "vcCompAttrComm")  
  
> [!NOTE]
>  Attributverwendung ändert nicht den Inhalt der Quelldatei.  Das Attribut nur der generierte Code ist während der Debugsitzungen sichtbar ist.  Außerdem für jede Quelldatei im Projekt, können Sie eine Textdatei generieren, die die Ergebnisse des Attributs ersatzes anzeigt.  Weitere Informationen zu diesem Verfahren finden Sie unter [\/Fx \(Zusammenführung eingefügter Code\)](../build/reference/fx-merge-injected-code.md) und [Eingefügten Code debuggen](../Topic/How%20to:%20Debug%20Injected%20Code.md).  
  
 Wie die meisten C\+\+\-Konstrukte Attribute verfügen über einen Satz von Eigenschaften, der die richtige Verwendung definiert.  Dies wird als der Kontext des Attributs und wird in der Tabelle Elementkontext Attribut für jedes Attribut im Referenzthema zur behoben werden.  Beispielsweise kann das [Co\-Klasse](../windows/coclass.md)\-Attribut auf einer vorhandenen Klasse oder Struktur, im Gegensatz zum [cpp\_quote](../windows/cpp-quote.md)\-Attribut nur angewendet werden, das überall in eine C\+\+\-Quelldatei eingefügt werden kann.  
  
## Siehe auch  
 [Concepts](../windows/attributed-programming-concepts.md)