---
title: Dokumentieren und Anzeigen von Klassen, die vom MFC-Anwendungs-Assistenten erstellt | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- document classes [MFC]
- document classes [MFC], created by application wizards
- application wizards [MFC], document/view classes created
- view classes [MFC], created by application wizards
ms.assetid: 70c34a60-2701-4981-acea-c08a5787d8e6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: eb1a1fc6c35bfb9589e827d798cb112640fa9b2f
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46417617"
---
# <a name="document-and-view-classes-created-by-the-mfc-application-wizard"></a>Mithilfe des MFC-Anwendungs-Assistenten erstellte Dokument- und Ansichtsklassen

MFC-Anwendung-Assistenten können Sie einen Vorsprung auf Ihrem Entwicklungs-Programm durch etwas grob strukturierte Dokument- und Ansichtsklassen für Sie zu erstellen. Sie können dann [ordnen Sie diese Klassen Befehle und Meldungen](../mfc/reference/mapping-messages-to-functions.md) und verwenden Sie die Visual C++ Quellcode-Editor, um deren Memberfunktionen schreiben.

Die Dokumentenklasse, die vom MFC-Anwendungs-Assistenten erstellte ergibt sich aus der Klasse [CDocument](../mfc/reference/cdocument-class.md). Die View-Klasse abgeleitet ist [CView](../mfc/reference/cview-class.md). Die Namen an, dass die Anwendungs-Assistent diese Klassen bietet und die Dateien, die sie enthalten auf den Namen des Projekts basieren Geben Sie im Dialogfeld Anwendungs-Assistenten. Im Anwendungs-Assistenten können Sie die Seite generierten Klassen, um die Standardnamen zu ändern.

Einige Anwendungen möglicherweise mehr als eine Dokumentklasse, Ansichtsklasse oder Rahmenfenster Klasse. Weitere Informationen finden Sie unter [mehrere Dokumenttypen, Ansichten und Frame Windows](../mfc/multiple-document-types-views-and-frame-windows.md).

## <a name="see-also"></a>Siehe auch

[Dokument-/Ansichtsarchitektur](../mfc/document-view-architecture.md)

