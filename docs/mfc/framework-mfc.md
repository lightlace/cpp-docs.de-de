---
title: Framework (MFC)
ms.date: 09/17/2019
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
ms.openlocfilehash: 387f53e3123b6863fcf218da39c7c5e356eb8219
ms.sourcegitcommit: 069e3833bd821e7d64f5c98d0ea41fc0c5d22e53
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2019
ms.locfileid: "74303415"
---
# <a name="framework-mfc"></a>Framework (MFC)

Ihre Arbeit mit dem MFC-Bibliotheks Framework (Microsoft Foundation Class) basiert größtenteils auf einigen Hauptklassen und mehreren visuellen C++ Tools. Einige Klassen Kapseln einen großen Teil der Win32-API (Application Programming Interface). Andere Klassen Kapseln Anwendungskonzepte, z. b. Dokumente, Ansichten und die Anwendung selbst. Andere kapseln OLE-Features und ODBC-und DAO-Datenzugriffs Funktionen.  (DAO wird durch Office 2013 unterstützt. DAO 3,6 ist die endgültige Version, die als veraltet eingestuft wird.)

Beispielsweise wird das Win32's-Konzept von Window von der MFC-Klasse `CWnd`gekapselt. Das heißt, eine C++ Klasse mit dem Namen `CWnd` kapselt oder umschließt das `HWND` handle, das ein Windows-Fenster darstellt. Ebenso kapselt Class `CDialog` Win32-Dialogfelder.

Kapselung bedeutet, C++ dass die-Klasse `CWnd`z. b. eine Member-Variable vom Typ `HWND`enthält, und die Member-Funktionen der Klasse Kapseln Aufrufe von Win32-Funktionen, die eine `HWND` als Parameter annehmen. Die Klassenmember-Funktionen haben normalerweise denselben Namen wie die Win32-Funktion, die Sie kapseln.

## <a name="in-this-section"></a>In diesem Abschnitt

[SDI und MDI](../mfc/sdi-and-mdi.md)

[Dokumente, Ansichten und das Framework](../mfc/documents-views-and-the-framework.md)

[Assistenten und Ressourcen-Editoren](../mfc/wizards-and-the-resource-editors.md)

## <a name="in-related-sections"></a>Verwandte Abschnitte

[Erstellen im Framework](../mfc/building-on-the-framework.md)

[So ruft das Framework Ihren Code auf](../mfc/how-the-framework-calls-your-code.md)

[CWinApp: Die Anwendungsklasse](../mfc/cwinapp-the-application-class.md)

[Dokumentvorlagen und der Erstellungsvorgang für Dokumente und Ansichten](../mfc/document-templates-and-the-document-view-creation-process.md)

[Meldungsbehandlung und Zuordnung](../mfc/message-handling-and-mapping.md)

[Fensterobjekte](../mfc/window-objects.md)

## <a name="see-also"></a>Siehe auch

[Verwenden der Klassen zum Schreiben von Anwendungen für Windows](../mfc/using-the-classes-to-write-applications-for-windows.md)
