---
title: Active Document-Container | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- active documents [MFC], containers
- containers [MFC], active document
- MFC, COM support
- active document containers [MFC], about active document containers
- MFC COM, active document containment
ms.assetid: b8dfa74b-75ce-47df-b75e-fc87b7f7d687
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 16c0311c3eedc13cbc47214b44fc8810dee3eecd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="active-document-containment"></a>Active Document-Container
Active Document-Container ist eine Technologie, die einen einzelnen Frame, in dem Sie arbeiten mit Dokumenten, anstatt Sie zu erstellen und verwenden mehrere Frames der Anwendung für jeden Dokumenttyp zwingen bereitstellt. Es unterscheidet sich vom einfachen OLE-Technologie, OLE mit eingebettete Objekte in ein Verbunddokument funktioniert nur ein einzelnes Stück des Inhalts aktiv sein kann. Mit active Document-Container aktivieren Sie ein ganzes Dokument (d. h. einer vollständigen Anwendung, einschließlich der zugehörigen Menüs, Symbolleisten und So weiter) innerhalb des Kontexts eines einzelnen Frames an.  
  
 Die active Document Containment-Technologie wurde ursprünglich für Microsoft Office, um Office Binder implementieren entwickelt. Allerdings ist die Technologie ist flexibel genug, um active Document-Container als Office Binder zu unterstützen und Dokumentserver als Office und Office-kompatiblen Anwendungen unterstützen kann.  
  
 Die Anwendung, aktive Dokumente hostet, heißt ein [active Document-Container](../mfc/active-document-containers.md). Beispiele für solche Container sind die Microsoft Office Binder oder Microsoft Internet Explorer.  
  
 Active Document-Container wird implementiert, wie ein Satz von Erweiterungen zu OLE-Dokumente, die Verbunddokumente-Technologie von OLE. Die Erweiterungen sind weitere Schnittstellen, mit die ein integrierbare, direkte-Objekt, das ein ganzes Dokument anstatt ein einzelnes Stück eingebetteter Inhalt darstellen können. Wie bei OLE-Dokumente verwendet active Document-Container einen Container, der dient der Anzeige für aktive Dokumente und Servern, auf denen der Benutzer-Schnittstelle und-Bearbeitung Funktionen für die aktive Dokumente selbst angeben.  
  
 Ein [active Document-Server](../mfc/active-document-servers.md) ist eine Anwendung (z. B. Word, Excel oder PowerPoint), unterstützt eine oder mehrere active Document-Klassen, jedes Objekt selbst, in denen die Schnittstellen, mit denen das Objekt unterstützt, das aktiviert werden können eine geeignete Container.  
  
 Ein [aktive Dokument](../mfc/active-documents.md) (bereitgestellt von einem aktiven Dokumentserver z. B. Word oder Excel) ist im Wesentlichen ein konventionelles Dokument, das als Objekt in einer anderen active Document-Container eingebettet ist. Im Gegensatz zu eingebetteten Objekten aktive Dokumente haben vollständige Kontrolle über ihre Seiten, und die vollständige Benutzeroberfläche der Anwendung (mit allen Befehlen und Tools) steht für den Benutzer zu bearbeiten.  
  
 Ein aktiven Dokuments verständlich ist am besten von einer standardmäßigen eingebetteten OLE-Objekts zu unterscheiden. Gemäß der Konvention OLE eingebettete Objekte sind, die auf der Seite des Dokuments angezeigt wird, die er besitzt, und das Dokument von einem OLE-Container verwaltet wird. Der Container speichert die Daten des eingebetteten Objekts mit dem Rest des Dokuments. Eingebettete Objekte sind jedoch beschränkt, als sie die Seite, auf denen sie angezeigt werden, nicht kontrollieren.  
  
 Benutzer einer containeranwendung für aktive Dokument können aktive Dokumente (so genannte Abschnitte in Office Binder) erstellen, die mit ihren bevorzugten Anwendungen (vorausgesetzt, dass diese Anwendungen aktive Dokument aktiviert sind), noch das daraus resultierende Projekt als die der Benutzer verwalten können eine Einheit eindeutig benannt werden kann gespeichert, gedruckt, und So weiter. Auf die gleiche Weise kann ein Benutzer von einem Internetbrowser die gesamte Netzwerk sowie lokalen Dateisystemen als einzelnes Dokument Speicherentität mit der Fähigkeit zum Durchsuchen der Dokumente in diesem Speicher an einem zentralen Ort behandeln.  
  
## <a name="sample-programs"></a>Beispielprogramme  
  
-   Die [MFCBIND](../visual-cpp-samples.md) Beispiel veranschaulicht die Implementierung einer containeranwendung für aktive Dokument.  
  
## <a name="see-also"></a>Siehe auch  
 [MFC COM](../mfc/mfc-com.md)

