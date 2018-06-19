---
title: Verwalten der Statusdaten von MFC-Modulen | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- global state [MFC]
- data management [MFC], MFC modules
- window procedure entry points [MFC]
- exported interfaces and global state [MFC]
- module states [MFC], saving and restoring
- data management [MFC]
- MFC, managing state data
- multiple modules [MFC]
- module state restored [MFC]
ms.assetid: 81889c11-0101-4a66-ab3c-f81cf199e1bb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9d87b2a601e6e25d61de6ca6ad639ac6a62861ac
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33347694"
---
# <a name="managing-the-state-data-of-mfc-modules"></a>Verwalten der Statusdaten von MFC-Modulen
Dieser Artikel beschreibt die Statusdaten von MFC-Modulen und wie dieser Status aktualisiert wird, wenn Sie der Fluss der Ausführung (im Path-Code findet sich durch eine Anwendung, für die Ausführung) erreicht oder verlässt ein Modul. Modulzustände mit Wechsel der `AFX_MANAGE_STATE` und `METHOD_PROLOGUE` Makros wird ebenfalls erläutert.  
  
> [!NOTE]
>  Das Begriff "Modul" Hier bezieht sich auf ein ausführbares Programm oder eine DLL (oder einen Satz von DLLs) an, die unabhängig von der Rest der Anwendung ausgeführt werden, verwendet jedoch eine gemeinsame Kopie der MFC-DLL. Ein ActiveX-Steuerelement ist ein typisches Beispiel für ein Modul.  
  
 Wie in der folgenden Abbildung dargestellt, hat MFC Statusdaten für jedes Modul in einer Anwendung verwendet. Beispiele für diese Daten sind Windows-Instanz-Handles (verwendet zum Laden von Ressourcen), Zeiger auf den aktuellen `CWinApp` und `CWinThread` Objekte von einer Anwendung, Verweiszähler für OLE-Modul und eine Vielzahl von Zuordnungen, die die Verbindungen zwischen verwalten Windows-Objekt behandelt und entsprechenden Instanzen von MFC-Objekten. Wenn eine Anwendung mehrere Module verwendet, das die Zustandsdaten der einzelnen Module ist jedoch nicht Anwendung breit. Stattdessen verfügt jedes Modul über eine eigene Kopie der Daten für die MFC-Zustand.  
  
 ![Zustandsdaten eines einzelmoduls &#40;Anwendung&#41;](../mfc/media/vc387n1.gif "vc387n1")  
Zustandsdaten eines Einzelmoduls (Anwendung)  
  
 Statusdaten für ein Modul ist in einer Struktur enthalten und ist immer über einen Zeiger auf dieser Struktur verfügbar. Wenn der Fluss der Ausführung ein bestimmtes Moduls eingibt, wie in der folgenden Abbildung gezeigt, muss der Status dieses Moduls den Status "Aktuell" oder "effektive" sein. Deshalb hat jede Threadobjekt einen Zeiger auf die gültige Statusstruktur dieser Anwendung. This-Zeiger überhaupt aktualisiert das schützen Zeiten ist ausschlaggebend, Verwalten von globalen Status der Anwendung sowie die Integrität des Status für jedes Modul. Eine fehlerhafte Verwaltung des globalen Status kann zu unvorhersehbarem Anwendungsverhalten führen.  
  
 ![Zustandsdaten mehrerer Module](../mfc/media/vc387n2.gif "vc387n2")  
Zustandsdaten mehrerer Module  
  
 Das heißt, ist jedes Modul für ordnungsgemäß Wechsel zwischen den Modulzustände aller seiner Einstiegspunkte verantwortlich. Ein "Einstiegspunkt" ist eine beliebige Stelle, in der Fluss der Ausführung des Moduls Code eingeben können. Einstiegspunkte sind:  
  
-   [Exportierte Funktionen in einer DLL](../mfc/exported-dll-function-entry-points.md)  
  
-   [Memberfunktionen von COM-Schnittstellen](../mfc/com-interface-entry-points.md)  
  
-   [Fensterprozeduren](../mfc/window-procedure-entry-points.md)  
  
## <a name="see-also"></a>Siehe auch  
 [Allgemeine MFC-Themen](../mfc/general-mfc-topics.md)

