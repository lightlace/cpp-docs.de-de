---
title: Dokument-/ Ansichtarchitektur
ms.date: 11/19/2018
helpviewer_keywords:
- CView class [MFC], view architecture
- CDocument class [MFC]
- MFC, views
- views [MFC], MFC document/view model
- document objects [MFC]
- document objects [MFC], MFC document/view model
- MFC, documents
- documents [MFC], MFC document/view model
- document objects [MFC], document/view architecture
ms.assetid: 6127768a-553f-462a-b01b-a5ee6068c81e
ms.openlocfilehash: d1b1f80f44fdc66a3174ea75c15e139f98a4520b
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/18/2019
ms.locfileid: "58775542"
---
# <a name="documentview-architecture"></a>Dokument-/Ansichtsarchitektur

Standardmäßig erstellt der MFC-Anwendung-Assistent ein Gerüst der Anwendung mit einer Dokumentklasse und eine View-Klasse. MFC trennt die datenverwaltung in diese beiden Klassen. Das Dokument speichert die Daten und Drucken der Daten und koordiniert das Aktualisieren von mehreren Ansichten der Daten. Die Ansicht werden die Daten angezeigt und verwaltet die Interaktion des Benutzers mit, einschließlich Auswahl und bearbeiten.

In diesem Modell wird ein MFC-Dokument-Objekt liest und schreibt Daten in den persistenten Speicher. Das Dokument kann auch eine Schnittstelle für die Daten bereitstellen, wo er sich befindet (z. B. in einer Datenbank). Ein separates Objekt verwaltet die Datenanzeige vom Rendern der Daten in einem Fenster zur Benutzerauswahl ein, und Bearbeiten von Daten. Die Ansicht Daten aus dem Dokument abgerufen und kommuniziert mit dem Dokument alle datenänderungen.

Während Sie ganz einfach außer Kraft setzen oder ignorieren die Trennung von Dokument/Ansicht, stehen zwingendsten Gründe für die dieses Modell in den meisten Fällen führen vor. Eine der besten ist, Sie mehrere Ansichten des gleichen Dokuments, z. B. sowohl eine Tabelle und eine Diagrammsicht benötigen. Das Dokument/ansichtsmodel kann ein separates Objekt jeder Ansicht der Daten, während Code, die allgemeine Darstellung für alle Ansichten (z. B. eine berechnungs-Engine) im Dokument gespeichert werden können. Das Dokument übernommen, der Task alle Sichten aktualisiert, bei jeder Datenänderung.

Der MFC Dokument-/Ansichtarchitektur erleichtert es, um mehrere Sichten, mehrere Dokumenttypen, Splitterfenster und andere wertvolle Benutzeroberflächen-Funktionen zu unterstützen.

Die Teile von MFC-Framework sichtbarste sowohl für den Benutzer als auch die Programmierer sind das Dokument und Ansicht. Die meisten Schritte bei der Entwicklung einer Anwendung mit dem Framework wird in Ihrem Dokument und Anzeigen von Klassen zu schreiben. Diese Artikelreihe beschreibt:

- Im Sinne von Dokumenten und Ansichten und wie sie in das Framework interagieren.

- Was Sie tun müssen, um diese zu implementieren.

Das Herzstück von Dokument/Ansicht stehen vier:

Die [CDocument](../mfc/reference/cdocument-class.md) (oder [COleDocument](../mfc/reference/coledocument-class.md)) Klasse unterstützt Objekte, die zum Speichern oder Ihres Programms Daten steuern und stellt die Basisfunktionen für Programmierer definierte Document-Klassen bereit. Ein Dokument repräsentiert die Einheit von Daten, die der Benutzer normalerweise mit dem Befehl "Öffnen" im Menü Datei öffnet und speichert mit dem Befehl "Speichern" im Menü Datei.

Die [CView](../mfc/reference/cview-class.md) (oder eines der vielen abgeleiteten Klassen) stellt die Basisfunktionen für Programmierer definierte Klassen bereit. Eine Sicht ist an ein Dokument angefügt und dient als Vermittler zwischen dem Dokument und der Benutzer: die Ansicht rendert ein Bild des Dokuments auf dem Bildschirm und Benutzereingaben als Vorgänge, bei dem Dokument interpretiert. Die Ansicht rendert auch das Bild zu drucken und Druckvorschau.

[CFrameWnd](../mfc/reference/cframewnd-class.md) (oder deren Varianten) unterstützt Objekte, die den Rahmen um eine oder mehrere Ansichten eines Dokuments enthält.

[CDocTemplate](../mfc/reference/cdoctemplate-class.md) (oder [CSingleDocTemplate](../mfc/reference/csingledoctemplate-class.md) oder [CMultiDocTemplate](../mfc/reference/cmultidoctemplate-class.md)) unterstützt ein Objekt, das eine oder mehrere vorhandene Dokumente eines bestimmten Typs koordiniert und verwaltet, erstellen den richtigen Dokument anzeigen und Frame-Windows-Objekte für diesen Typ.

Die folgende Abbildung zeigt die Beziehung zwischen einem Dokument und dessen Ansicht.

![Die Ansicht ist Teil des Dokuments, das angezeigt wird,](../mfc/media/vc379n1.gif "Ansicht ist Teil des Dokuments, das angezeigt wird") <br/>
Dokument und Ansicht

Die Implementierung von Dokument/Ansicht, in der Klassenbibliothek trennt die Daten selbst die Anzeige von Benutzervorgänge für die Daten. Alle Änderungen an den Daten werden über die Dokumentklasse verwaltet. Die Ansicht ruft diese Schnittstelle, um den Zugriff auf und die Daten aktualisieren.

Dokumente, die zugehörigen Ansichten und die Frame-Fenster, die frame-Ansichten werden von einer Dokumentvorlage erstellt. Die Dokumentvorlage dient zum Erstellen und verwalten alle Dokumente eines Dokumenttyps.

## <a name="what-do-you-want-to-know-more-about"></a>Was möchten Sie mehr erfahren

- [Ein Portrait der Dokument-/Ansichtarchitektur](../mfc/a-portrait-of-the-document-view-architecture.md)

- [Vorteile der Dokument-/Ansichtarchitektur](../mfc/advantages-of-the-document-view-architecture.md)

- [Dokument und Ansicht-Klassen, die vom Anwendungs-Assistenten erstellt](../mfc/document-and-view-classes-created-by-the-mfc-application-wizard.md)

- [Alternativen zur Dokument-/Ansichtarchitektur](../mfc/alternatives-to-the-document-view-architecture.md)

- [Hinzufügen mehrerer Ansichten zu einem Dokument](../mfc/adding-multiple-views-to-a-single-document.md)

- [Verwenden von Dokumenten](../mfc/using-documents.md)

- [Verwenden von Ansichten](../mfc/using-views.md)

- [Mehrere Dokumenttypen, Ansichten und Rahmenfenster](../mfc/multiple-document-types-views-and-frame-windows.md)

- [Initialisieren und Bereinigen von Dokumenten und Ansichten](../mfc/initializing-and-cleaning-up-documents-and-views.md)

- [Initialisieren Sie Ihre eigenen Erweiterungen Dokument und Ansicht-Klassen](../mfc/creating-new-documents-windows-and-views.md)

- [Verwenden von Datenbankklassen mit Dokumenten und Ansichten](../data/mfc-using-database-classes-with-documents-and-views.md)

- [Verwenden von Datenbankklassen ohne Dokumente und Ansichten](../data/mfc-using-database-classes-without-documents-and-views.md)

- [Beispiele](../overview/visual-cpp-samples.md)

## <a name="see-also"></a>Siehe auch

[Elemente der Benutzeroberfläche](../mfc/user-interface-elements-mfc.md)<br/>
[Windows](../mfc/windows.md)<br/>
[Rahmenfenster](../mfc/frame-windows.md)<br/>
[Dokumentvorlagen und der Erstellungsvorgang für Dokumente und Ansichten](../mfc/document-templates-and-the-document-view-creation-process.md)<br/>
[Erstellen von Dokument/Ansicht](../mfc/document-view-creation.md)<br/>
[Erstellen neuer Dokumente, Fenster und Ansichten](../mfc/creating-new-documents-windows-and-views.md)
