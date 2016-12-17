---
title: "Beziehung zum C-Sprachen-API"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "vc.classes.mfc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Bücher [C++]"
  - "Bücher [C++], Informationen über MFC und Windows SDK"
  - "MFC [C++], Windows-API"
  - "Visual C, Windows-API-Aufrufe"
  - "Windows-API [C++], und MFC"
ms.assetid: 334e8efc-f3cc-4018-bc2e-02908b2a39fe
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Beziehung zum C-Sprachen-API
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Das einzelne Merkmal, das die MFC\-Bibliothek \(Microsoft Foundation Class \(MFC\) abgesehen von anderen Klassenbibliotheken für Windows festlegen, ist sehr nahe Zuordnung zur Windows\-API, die in die Programmiersprache C geschrieben wird.  Außerdem können Sie Aufrufe zur Klassenbibliothek mit direkten Aufrufen zur Windows\-API im Allgemeinen frei kombinieren.  Dieser Direktzugriff bedeutet nicht jedoch, dass die Klassen ein vollständiger Für diese API.  Entwickler müssen direkte Aufrufe an einige Windows\-Funktionen, wie [SetCursor](http://msdn.microsoft.com/library/windows/desktop/ms648393) und [GetSystemMetrics](http://msdn.microsoft.com/library/windows/desktop/ms724385) jedoch gelegentlich machen, z. B  Eine Windows\-Funktion wird durch eine Klassenmemberfunktion umschlossen, wenn es einen klaren Vorteil der dazu gibt.  
  
 Da Sie auch systemeigene Windows\-Funktions\-Aufrufe ausführen müssen, sollten Sie der Sprache C Windows\-API\-Dokumentation haben.  Diese Dokumentation wird mit Microsoft Visual C\+\+ enthalten.  
  
> [!NOTE]
>  Eine Übersicht darüber, wie das MFC\-Bibliotheksframework funktioniert, finden Sie unter [Verwenden von Klassen, die von Anwendungen für Windows zu schreiben](../mfc/using-the-classes-to-write-applications-for-windows.md).  
  
## Siehe auch  
 [Allgemeine Prinzipien für den Klassenentwurf](../mfc/general-class-design-philosophy.md)