---
title: Einfügen eines Formulars in einem Projekt | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- inserting forms [MFC]
- Insert New dialog box [MFC]
- forms, adding to projects
ms.assetid: f3bd2998-3ce2-496d-ac5c-57ca70eec7cb
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ba22c87ee601d66ccfb1092047e69be42d8163c3
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/25/2018
ms.locfileid: "50052751"
---
# <a name="inserting-a-form-into-a-project"></a>Einfügen eines Formulars in ein Projekt

Forms stellen einen praktischer Container für Steuerelemente bereit. Sie können eine MFC-basiertes Formular einfach in Ihre Anwendung einfügen, solange die Anwendung die MFC-Bibliotheken unterstützt.

### <a name="to-insert-a-form-into-your-project"></a>Um ein Formular in das Projekt einfügen.

1. Wählen Sie aus der Klassenansicht das Projekt, zu dem Sie die Form hinzufügen möchten, und klicken Sie auf der rechten Maustaste.

1. Klicken Sie im Kontextmenü auf **hinzufügen** , und klicken Sie dann auf **Klasse hinzufügen**.

   Wenn die **Formulars** Befehl ist nicht verfügbar, die Ihr Projekt basiert möglicherweise auf die Active Template Library (ATL). Um ein ATL-Projekt ein Formular hinzugefügt haben, müssen Sie [Geben Sie bestimmte Einstellungen](../atl/reference/application-settings-atl-project-wizard.md) beim ersten Erstellen des Projekts.

1. Von der **MFC** Ordner, klicken Sie auf **MFC-Klasse**.

1. Mit der MFC-Klassen-Assistenten legen Sie die neue Klasse, die abgeleitet [CFormView](../mfc/reference/cformview-class.md).

Visual C++ fügt das Formular an Ihre Anwendung in den Dialog-Editor öffnen, damit Sie beginnen, Hinzufügen von Steuerelementen und der Gesamtentwurf gearbeitet.

Möglicherweise möchten die folgenden zusätzlichen Schritte (gilt nicht für Dialogfeld-basierte Anwendungen) ausführen:

1. Überschreiben der `OnUpdate` Member-Funktion.

1. Implementieren Sie eine Memberfunktion zum Verschieben von Daten aus der Ansicht in Ihr Dokument.

1. Erstellen Sie eine `OnPrint` Member-Funktion.

## <a name="see-also"></a>Siehe auch

[Formularansichten](../mfc/form-views-mfc.md)

