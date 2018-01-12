---
title: Aktive Dokumentserver | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- active documents [MFC], servers
- servers [MFC], active document
- active document servers [MFC]
ms.assetid: 131fec1e-02a0-4305-a7ab-903b911232a7
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3dacb923b2e51ddc031165e637b08c9614ee1bf3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="active-document-servers"></a>Server für aktive Dokumente
Aktive Dokumentserver wie z. B. Word-, Excel- oder PowerPoint-Host-Dokumente von anderen Anwendungstypen genannten active Documents. Im Gegensatz zu OLE eingebettete Objekte (die einfach in die Seite von einem anderen Dokument angezeigt werden), aktive Dokumente bieten die vollständige Benutzeroberfläche und die vollständige systemeigene Funktionalität der Server-Anwendung, die sie erstellt. Benutzer können Dokumente erstellen, verwenden die volle Leistung von ihren bevorzugten Anwendungen (Wenn sie aktive Dokument aktiviert sind), noch können behandeln das daraus resultierende Projekt als eine Einheit.  
  
 Aktive Dokumente können über mehrere Seiten und sind immer in-Place aktiv. Aktive Dokumente steuern Teil der Benutzeroberfläche, indem Sie ihre Menüs mit der **Datei** und **Hilfe** Menüs des Containers. Belegt den gesamten Bearbeitungsbereich des Containers, und die Ansichten und das Layout der Seite "Drucker" (Ränder, Fußzeilen usw.) zu steuern.  
  
 MFC implementiert aktive Dokumentserver mit Dokument-/Ansichtarchitektur Schnittstellen, Befehl Dispatchzuordnungen, drucken, Menü-Management und Registrierung Management. Anforderungen für bestimmte Programmiersprache finden Sie im Abschnitt [aktive Dokumente](../mfc/active-documents.md).  
  
 MFC unterstützt aktive Dokumente mit den [CDocObjectServer](../mfc/reference/cdocobjectserver-class.md) von abgeleitete Klasse [CCmdTarget](../mfc/reference/ccmdtarget-class.md), und [CDocObjectServerItem](../mfc/reference/cdocobjectserveritem-class.md), abgeleitet von [ COleServerItem](../mfc/reference/coleserveritem-class.md). MFC unterstützt active Document-Container mit dem [COleDocObjectItem](../mfc/reference/coledocobjectitem-class.md) von abgeleitete Klasse [COleClientItem](../mfc/reference/coleclientitem-class.md).  
  
 `CDocObjectServer`Ordnet die active Document-Schnittstellen und initialisiert, und ein aktiven Dokuments aktiviert. MFC enthält außerdem Makros um Befehlsrouting in aktive Dokumente zu verarbeiten. Um die aktive Dokumente in Ihrer Anwendung verwenden, Sie AfxDocOb.h in der Datei "stdafx.h".  
  
 Ein normaler MFC-Server nimmt eine eigene `COleServerItem`-Klasse. Die MFC-Anwendungs-Assistent diese Klasse für Sie erstellt, bei Auswahl der **Miniserver** oder **Vollserver** Kontrollkästchen, um Ihre Anwendung Unterstützung für Verbunddokumente einzuräumen. Wenn Sie auch auswählen, die **Active Document-Server** Kontrollkästchen, die MFC-Anwendungs-Assistent erstellt eine Klasse abgeleitet wurde. `CDocObjectServerItem` stattdessen.  
  
 Die `COleDocObjectItem` -Klasse ermöglicht es, einen active Document-Container werden OLE-Container. Können Sie den MFC-Anwendung-Assistenten erstellen Sie einen active Document-Container durch Auswahl der **Active Document-Container** Verbunddokumente Seite des Assistenten für MFC-Anwendung in. Weitere Informationen finden Sie unter [Erstellen einer Containeranwendung für aktive Dokumente](../mfc/creating-an-active-document-container-application.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Aktive Dokumente-Container](../mfc/active-document-containment.md)

