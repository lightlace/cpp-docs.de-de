---
title: Active Document-Container
ms.date: 11/04/2016
helpviewer_keywords:
- active documents [MFC], containers
- containers [MFC], active document
- MFC, COM support
- active document containers [MFC], about active document containers
- MFC COM, active document containment
ms.assetid: b8dfa74b-75ce-47df-b75e-fc87b7f7d687
ms.openlocfilehash: dc13384454c4732d3efbf99def5d05dd4f2d44aa
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2019
ms.locfileid: "58776569"
---
# <a name="active-document-containment"></a>Active Document-Container

Active Document-Container ist eine Technologie, die ein einzelnes Frame, in dem bietet Sie arbeiten mit Dokumenten, anstatt Sie zu erstellen und verwenden mehrere Frames der Anwendung für jeden Dokumenttyp zwingen. Es unterscheidet sich vom einfachen OLE-Technologie, OLE mit eingebetteten Objekten in einem Verbunddokument funktioniert in der nur ein einzelnes Inhaltselement aktiv sein kann. Mit active Document-Container aktivieren Sie ein ganzes Dokument (d. h. eine vollständige Anwendung, einschließlich der zugehörigen Menüs, Symbolleisten und So weiter), im Kontext eines einzelnen Frames.

Die active Document Containment-Technologie wurde ursprünglich für Microsoft Office, Office Binder implementiert entwickelt. Allerdings ist die Technologie ist flexibel genug, um active Document-Container als Office Binder zu unterstützen und Dokumentserver als Office und Office-kompatiblen Anwendungen unterstützen.

Die Anwendung, aktive Dokumente hostet, heißt ein [active Document-Container](../mfc/active-document-containers.md). Beispiele für solche Container sind die Microsoft Office Binder oder Microsoft Internet Explorer.

Active Document-Container wird implementiert, wie ein Satz von Erweiterungen zu OLE-Dokumente, die Verbunddokument-Technologie von OLE. Die Erweiterungen sind weitere Schnittstellen, mit die ein eingebettet werden, ein direktes Objekt ein ganzes Dokument anstelle eines einzelnen Teils eingebetteter Inhalt darstellen können. Wie bei der OLE-Serverdokumente, verwendet active Document-Container einen Container, der den Anzeigebereich für aktive Dokumente und -Server, die der Benutzer für die aktive Dokumente selbst-Schnittstelle und-Bearbeitung ermöglichen bereitstellt.

Ein [active Document-Server](../mfc/active-document-servers.md) ist eine Anwendung (z. B. Word, Excel oder PowerPoint), die eine oder mehrere active Document-Klassen unterstützt, in dem jedes Objekt selbst die Schnittstellen der datenverarbeitungserweiterung, mit denen das Objekt unterstützt, das in aktiviert werden können. ein geeignete Container.

Ein [aktive Dokument](../mfc/active-documents.md) (bereitgestellt von einem aktiven Dokumentserver wie Word oder Excel) ist im Wesentlichen ein konventionelles Dokument, das als ein Objekt in einer anderen active Document-Container aus eingebettet ist. Im Gegensatz zu eingebetteten Objekten die aktive Dokumente haben vollständige Kontrolle über ihre Seiten aus, und die vollständige Benutzeroberfläche der Anwendung (mit allen Befehlen und Tools) für den Benutzer zu deren Bearbeitung verfügbar ist.

Ein aktives Dokument besser zu verstehen unterscheiden sie von einem standard eingebettete OLE-Objekt. Klicken Sie nach OLE-Konvention ein eingebettetes Objekt ist eine, die auf der Seite des Dokuments angezeigt wird, die dieser besitzt, und das Dokument von einem OLE-Container verwaltet wird. Der Container enthält die eingebetteten Daten des Objekts mit dem Rest des Dokuments. Eingebettete Objekte sind jedoch begrenzt, als sie die Seite, auf dem sie angezeigt werden, nicht kontrollieren.

Benutzer von einer containeranwendung für aktive Dokument können aktive Dokumente (Abschnitte in Office Binder bezeichnet) erstellen ihre bevorzugten Anwendungen verwenden, (vorausgesetzt, diese Anwendungen aktive Dokument aktiviert sind), aber der Benutzer das resultierende Projekt als verwalten können eine einzelne Entität, die einen eindeutigen Namen haben kann gespeichert, gedruckt, und So weiter. Auf die gleiche Weise kann ein Benutzer einen Internet-Browser das gesamte Netzwerk als auch lokale Dateisysteme, wie eine Speicherentität für einzelnes Dokument mit der Möglichkeit, die Dokumente in diesem Speicher an einem zentralen Ort zu durchsuchen behandelt werden.

## <a name="sample-programs"></a>Beispielprogramme

- Die [MFCBIND](../overview/visual-cpp-samples.md) Beispiel veranschaulicht die Implementierung einer containeranwendung für aktive Dokument.

## <a name="see-also"></a>Siehe auch

[MFC COM](../mfc/mfc-com.md)
