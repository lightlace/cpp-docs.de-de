---
title: Framework (MFC)
ms.date: 11/04/2016
helpviewer_keywords:
- encapsulation [MFC], Win32 API
- MFC, application framework
- wrapper classes [MFC], explained
- Win32 [MFC], API encapsulation by MFC
- application framework [MFC], about MFC application framework
- APIs [MFC], encapsulation by MFC Win32
- encapsulation [MFC]
- Windows API [MFC], encapsulation by MFC
- encapsulated Win32 API [MFC]
ms.assetid: 3be0fec8-9843-4119-ae42-ece993ef500b
ms.openlocfilehash: 933fcf97c24ed0903395e2c718f8c89d42473494
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2019
ms.locfileid: "57269018"
---
# <a name="framework-mfc"></a>Framework (MFC)

Die Arbeit mit dem Framework für die Microsoft Foundation Class (MFC)-Bibliothek basiert größtenteils auf einige wichtige Klassen und verschiedene Tools für Visual C++. Einige Klassen kapseln einen großen Teil der Win32-Anwendungsprogrammierschnittstelle (API). Andere Klassen kapseln Anwendungskonzepte wie z. B. Dokumente, Ansichten und die Anwendung selbst. Weiterhin kapseln andere OLE-Features und Funktionen von ODBC und DAO-Datenzugriff.

Win32 Konzept der Fenster ist z. B. von MFC-Klasse gekapselt `CWnd`. Das heißt, eine C++-Klasse aufgerufen `CWnd` kapselt, oder "umschließt" die `HWND` Handle, das ein Windows-Fenster darstellt. Ebenso Klasse `CDialog` Win32-Dialogfelder kapselt.

Kapselung bedeutet, dass die C++-Klasse `CWnd`, enthält z. B. eine Membervariable des Typs `HWND`, und Memberfunktionen der Klasse gekapselt werden Aufrufe von Win32-Funktionen, die akzeptieren ein `HWND` als Parameter. Klassenmemberfunktionen haben in der Regel den gleichen Namen wie die Win32-Funktion, die sie kapseln.

## <a name="in-this-section"></a>In diesem Abschnitt

[SDI und MDI](../mfc/sdi-and-mdi.md)

[Dokumente, Ansichten und das Framework](../mfc/documents-views-and-the-framework.md)

[Assistenten und die Ressourcen-Editoren](../mfc/wizards-and-the-resource-editors.md)

## <a name="in-related-sections"></a>In verwandten Abschnitten

[Erstellen im Framework](../mfc/building-on-the-framework.md)

[So ruft das Framework Ihren Code auf](../mfc/how-the-framework-calls-your-code.md)

[CWinApp: Die Anwendungsserver-Klasse](../mfc/cwinapp-the-application-class.md)

[Dokumentvorlagen und der Erstellungsvorgang für Dokumente und Ansichten](../mfc/document-templates-and-the-document-view-creation-process.md)

[Meldungsbehandlung und Zuordnung](../mfc/message-handling-and-mapping.md)

[Fensterobjekte](../mfc/window-objects.md)

## <a name="see-also"></a>Siehe auch

[Verwenden der Klassen zum Schreiben von Anwendungen für Windows](../mfc/using-the-classes-to-write-applications-for-windows.md)
