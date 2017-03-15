---
title: "OLE-Hintergrund: Verlinken und Einbetten | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Eingebettete Objekte [C++]"
  - "Elementtypen"
  - "Elementtypen, Definition"
  - "verknüpfte Elemente (OLE) [C++]"
  - "OLE-Elemente (eingebettet)"
  - "OLE-Elemente, Typen"
  - "OLE, verknüpfte Elemente"
ms.assetid: 11107711-eb96-4099-8f5c-7910bb3ecb75
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# OLE-Hintergrund: Verlinken und Einbetten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Verwenden des Pastenbefehls in einer Containeranwendung kann eine eingebettete Komponente erstellen oder wie das Element ein.  Die Quelldaten für ein eingebettetes Element werden als Teil des OLE\-Dokuments gespeichert, das es enthält.  Auf diese Weise kann eine Dokumentdatei für ein Textverarbeitungsprogrammdokument Text enthalten kann und Bitmaps, Diagramme, Formeln oder einen anderen Typ außerdem Daten enthalten.  
  
 OLE bietet eine andere Möglichkeit, Daten von einer anderen Anwendung zu speichern: Erstellen einer verknüpften Komponente oder verknüpften Elements oder ein Link.  Die Schritte zum Erstellen eines verknüpften Elements sind mit denen für das Erstellen eines eingebetteten Elemente ähnlich, außer dass Sie verwenden den Pasten\-Linkbefehl anstelle des Pastenbefehls.  Anders als eingebettete Komponente speichert eine verknüpfte Komponente einen Pfad auf die ursprünglichen Daten, die häufig in einer separaten Datei befindet.  
  
 Wenn Sie in einem Textverarbeitungsprogrammdokument arbeiten und ein verknüpftes Element zu einigen Arbeitsblattzellen erstellen, werden die Daten für das verknüpfte Element im Arbeitsblattdokument originalen gespeichert.  Das Textverarbeitungsprogrammdokument enthält nur die Informationen, die angeben, wo das Element gefunden werden kann, d h. ein Link zum Arbeitsblattdokument originalen enthält.  Wenn Sie auf die Zellen doppelklicken, wird die Arbeitsblatt\-Anwendung gestartet und die ursprünglichen Arbeitsblattdokument wird geladen aus, in der es gespeichert wurde.  
  
 Jedes OLE\-Element, ob eingebettet bzw. verknüpft, hat einen Typ, der mit dem auf der Anwendung zugeordnet wird, die es erstellt hat.  Beispielsweise ist ein Microsoft\-Paintbrushelement ein Elementtyp, und ein Microsoft Excel\-Element ist ein anderer Typ.  Einige Anwendungen können mehrere Elementtyp jedoch erstellen.  Beispielsweise kann Microsoft Excel Arbeitsblattelemente Diagrammelemente, und macrosheet Elemente erstellen.  Jedes dieser Elemente kann vom System mit einer oder **CLSID**\-Klassenbezeichner eindeutig identifiziert werden.  
  
## Siehe auch  
 [OLE\-Hintergrund](../mfc/ole-background.md)   
 [OLE\-Hintergrund: Container und Server](../mfc/ole-background-containers-and-servers.md)   
 [Container: Clientelemente](../mfc/containers-client-items.md)   
 [Server: Serverelemente](../mfc/servers-server-items.md)