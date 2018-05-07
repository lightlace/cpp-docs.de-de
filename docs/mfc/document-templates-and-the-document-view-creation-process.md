---
title: Dokumentvorlagen und der Erstellungsvorgang Dokument Ansichten | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- icons, for multiple document templates
- document templates [MFC], and views
- document/view architecture [MFC], creating document/view
- single document template
- MFC, document templates
- multiple document template
- CDocTemplate class [MFC]
- templates [MFC], document templates
ms.assetid: 311ce4cd-fbdf-4ea1-a51b-5bb043abbcee
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f2d8308e69cf53db4be51f6ce742df41edaa89ea
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="document-templates-and-the-documentview-creation-process"></a>Dokumentvorlagen und der Erstellungsvorgang für Dokumente und Ansichten
Zur Verwaltung der komplexen Vorgang des Erstellens von Dokumenten mit ihren zugehörigen Ansichten und Rahmenfenster verwendet das Framework zwei Dokumentvorlagenklassen: [CSingleDocTemplate](../mfc/reference/csingledoctemplate-class.md) für SDI-Anwendungen und [CMultiDocTemplate ](../mfc/reference/cmultidoctemplate-class.md) für MDI-Anwendungen. Ein `CSingleDocTemplate` erstellen und speichern Sie ein Dokument von einem Typ zu einem Zeitpunkt können. Ein `CMultiDocTemplate` hält eine Liste viele geöffnete Dokumente eines bestimmten Typs.  
  
 Einige Anwendungen unterstützen mehrere Dokumenttypen. Eine Anwendung kann z. B. Textdokumente und Grafikdokumente unterstützen. Wenn der Benutzer den neuen Befehl im Menü Datei auswählt, zeigt ein Dialogfeld in einer Anwendung eine Liste der neuen Dokumenttypen zu öffnen. Für jeden unterstützten Dokumenttyp verwendet die Anwendung ein bestimmtes Dokumentvorlagenobjekt. Die folgende Abbildung veranschaulicht die Konfiguration einer MDI-Anwendung, die zwei Dokumenttypen unterstützt und mehrere offene Dokumente anzeigt.  
  
 ![MDI-Anwendung mit zwei Dokumenttypen](../mfc/media/vc387h1.gif "vc387h1")  
MDI-Anwendung mit zwei Dokumenttypen  
  
 Dokumentvorlagen erstellt und verwaltet, die durch das Anwendungsobjekt. Einer der wichtigsten Aufgaben ausgeführt, während der Anwendungsverzeichnis `InitInstance` Funktion besteht darin, eine oder mehrere Dokumentvorlagen des entsprechenden Typs zu erstellen. Diese Funktion ist in der beschriebenen [Erstellen von Dokumentvorlagen](../mfc/document-template-creation.md). Das Anwendungsobjekt speichert einen Zeiger auf jede Dokumentvorlage in der Vorlagenliste und stellt eine Schnittstelle für das Hinzufügen von Dokumentvorlagen.  
  
 Wenn Sie zwei oder mehr Dokumenttypen unterstützen müssen, müssen Sie einen zusätzlichen Aufruf hinzufügen [AddDocTemplate](../mfc/reference/cwinapp-class.md#adddoctemplate) für jeden Dokumenttyp.  
  
 Ein Symbol wird für jedes Dokumentvorlage anhand seiner Position in der Liste der Anwendung von Dokumentvorlagen registriert. Die Reihenfolge der Dokumentvorlagen richtet sich nach der Reihenfolge, werden sie durch Aufrufe von hinzugefügt `AddDocTemplate`. MFC wird davon ausgegangen, dass die erste Symbolressource in der Anwendung ist das Symbol "Anwendung", weitere Symbolressource ist die erste Dokumentsymbol und So weiter.  
  
 Beispielsweise ist eine Dokumentvorlage, die dritte von drei für die Anwendung. Wenn in der Anwendung am Index 3 Symbolressource vorhanden ist, wird das Symbol für das Dokumentvorlage verwendet. Wenn dies nicht der Fall ist, wird das Symbol "bei Index 0 wird als Standardwert verwendet.  
  
## <a name="see-also"></a>Siehe auch  
 [Allgemeine MFC-Themen](../mfc/general-mfc-topics.md)   
 [Erstellen von Dokumentvorlagen](../mfc/document-template-creation.md)   
 [Erstellen von Dokument/Ansicht](../mfc/document-view-creation.md)   
 [Beziehungen zwischen MFC-Objekte](../mfc/relationships-among-mfc-objects.md)   
 [Erstellen neuer Dokumente, Fenster und Ansichten](../mfc/creating-new-documents-windows-and-views.md)

