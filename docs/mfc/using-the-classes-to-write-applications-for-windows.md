---
title: Verwenden der Klassen zum Schreiben von Anwendungen für Windows | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- Windows applications [MFC], MFC application framework
- MFC, application development
- applications [OLE], MFC application framework
- MFC ActiveX controls [MFC], creating
- OLE applications [MFC], MFC application framework
- database applications [MFC], creating
ms.assetid: 73f63470-857d-43dd-9a54-b38b7be0f1b7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c60cf5d6f61f16aac18524e8b6e75638ec13d27e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46433334"
---
# <a name="using-the-classes-to-write-applications-for-windows"></a>Verwenden der Klassen zum Schreiben von Anwendungen für Windows

Zusammen machen die Klassen in der Microsoft Foundation Class (MFC)-Bibliothek "Anwendungsframework," auf dem Sie eine Anwendung für das Windows-Betriebssystem erstellen. Auf einer sehr allgemeinen Ebene das Framework das Gerüst einer Anwendung definiert und stellt die standardmäßigen Benutzeroberflächen-Implementierungen, die in das Gerüst platziert werden können. Ihre Aufgabe als Programmierer werden im weiteren Verlauf das Gerüst, füllen die sind Dinge, die für Ihre Anwendung spezifisch sind. Sie können einen Vorsprung abrufen, indem Sie mithilfe des MFC-Assistenten zum Erstellen der Dateien für eine sehr umfassende startanwendung. Können Sie die Microsoft Visual C++ Ressourcen-Editoren um Ihre Elemente der Benutzeroberfläche visuell zu entwerfen Klassenansicht Befehle aus, um diese Elemente mit Code und die Klassenbibliothek herstellen eine anwendungsspezifische Logik implementieren.

Version 3.0 und höher von MFC-Framework unterstützt die Programmierung für Win32-Plattformen, einschließlich Microsoft Windows 95 und höher und Windows NT, Version 3.51 und höher. MFC-Win32-Unterstützung umfasst multithreading. Verwenden Sie Version 1.5*x* bei Bedarf 16-Bit-Programmierung zu tun.

Diese Artikelreihe bietet eine grobe Übersicht über das Anwendungsframework. Es beschreibt auch die wichtigsten Objekte, aus denen Ihre Anwendung und wie sie erstellt werden. Sind Sie die folgenden Schritte aus, für die Themen in den folgenden Artikeln:

- [Das Framework](../mfc/framework-mfc.md).

- Meistens zwischen dem Framework und dem Code, wie in beschrieben [erstellen im Framework](../mfc/building-on-the-framework.md).

- [Die Anwendungsklasse](../mfc/cwinapp-the-application-class.md), die auf Anwendungsebene-Funktionalität kapselt.

- Wie [Dokumentvorlagen](../mfc/document-templates-and-the-document-view-creation-process.md) erstellen und Verwalten von Dokumenten und ihre zugehörigen Ansichten und Rahmenfenster.

- Klasse [CWnd](../mfc/window-objects.md), die Stamm-Basisklasse aller Fenster.

- [Grafikobjekte](../mfc/graphic-objects.md), z. B. Stifte und Pinsel.

Andere Teile von Framework enthalten:

- [Fensterobjekte: Übersicht](../mfc/window-objects.md)

- [Meldungsbehandlung und Zuordnung](../mfc/message-handling-and-mapping.md)

- [CObject, die Stamm-Basisklasse in MFC](../mfc/using-cobject.md)

- [Dokument-/Ansichtsarchitektur](../mfc/document-view-architecture.md)

- [Dialogfelder](../mfc/dialog-boxes.md)

- [Steuerelemente](../mfc/controls-mfc.md)

- [Steuerleisten](../mfc/control-bars.md)

- [OLE](../mfc/ole-in-mfc.md)

- [Speicherverwaltung](../mfc/memory-management.md)

     Abgesehen davon, dass Sie einen Vorteil beim Schreiben von Anwendungen für das Windows-Betriebssystem, erleichtert MFC auch zum Schreiben von Anwendungen, die speziell OLE verlinken und Einbetten von Technologie zu verwenden. Sie können die Anwendung machen eine OLE visual bearbeiten, Container, eine visual bearbeiten OLE-Server oder beides aus, und Sie können Automation hinzufügen, sodass andere Anwendungen können Objekte aus Ihrer Anwendung verwenden oder auch remote steuern.

- [MFC-ActiveX-Steuerelemente](../mfc/mfc-activex-controls.md)

     Das OLE-Steuerelement Development Kit (CDK) ist jetzt vollständig in das Framework integriert. Diese Artikelreihe bietet einen Überblick über die Entwicklung von ActiveX-Steuerelementen mit MFC. (ActiveX-Steuerelemente wurden früher als OLE-Steuerelemente bezeichnet.)

- [Datenbankprogrammierung](../data/data-access-programming-mfc-atl.md)

     MFC bietet zudem zwei Sätze von Datenbankklassen, die schreiben-Datenzugriff zu vereinfachen Anwendungen. Verwenden die ODBC-Datenbankklassen, Sie Verbindungen mit Datenbanken über einen Treiber Open Database Connectivity (ODBC) herstellen, auswählen von Datensätzen aus Tabellen, und anzeigen können Aufzeichnen von Informationen in einem Formular auf dem Bildschirm. Verwenden die Klassen (Data Access Object, DAO), können Sie dann, mit Datenbanken über das Microsoft Jet-Datenbank-Engine oder die externe (nicht-Jet-) Datenquellen, einschließlich der ODBC-Datenquellen arbeiten.

     Darüber hinaus MFC ist vollständig für das Schreiben von Anwendungen, die Unicode verwenden aktiviert und Mehrbyte-Zeichensätzen (MBCS), insbesondere Doppelbyte-Zeichensätze (DBCS).

Allgemeine Hinweise zu MFC-Dokumentation, finden Sie unter [allgemeine MFC-Themen](../mfc/general-mfc-topics.md).

## <a name="see-also"></a>Siehe auch

[Allgemeine MFC-Themen](../mfc/general-mfc-topics.md)

