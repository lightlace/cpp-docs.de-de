---
title: ON_UPDATE_COMMAND_UI-Makro | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- ON_UPDATE_COMMAND_UI
dev_langs:
- C++
helpviewer_keywords:
- ON_UPDATE_COMMAND_UI macro [MFC]
- update handlers [MFC]
- command-handler macros
- updating user-interface objects [MFC]
ms.assetid: 3e72b50f-4119-4c82-81cf-6e09b132de05
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 17111e24a63d527996eadd82c804e5147ad78552
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/19/2018
ms.locfileid: "46433464"
---
# <a name="onupdatecommandui-macro"></a>ON_UPDATE_COMMAND_UI Macro

Verwenden der **Eigenschaften** Fenster aus, um die Verbindung mit Befehlsaktualisierungs Handler in einer Befehlszielobjekt ein Benutzeroberflächen-Objekt. Es wird automatisch verbinden die Benutzeroberflächen-ID des Objekts mit der ON_UPDATE_COMMAND_UI-Makro und erstellen Sie einen Ereignishandler in das Objekt, das Update behandelt wird. Finden Sie unter [Zuordnen von Meldungen zu Funktionen](../mfc/reference/mapping-messages-to-functions.md) für Weitere Informationen.

Um einen Befehl alle Löschen Ihres Programms Menü "Bearbeiten" zu aktualisieren, verwenden Sie z. B. die **Eigenschaften** Fenster eine Meldungszuordnungseintrags in der ausgewählten Klasse eine Funktionsdeklaration für ein Befehlsaktualisierungshandler hinzufügen mit der Bezeichnung `OnUpdateEditClearAll` in der Klasse Deklaration und eine leere Funktion-Vorlage in der Implementierungsdatei der Klasse. Der Funktionsprototyp sieht folgendermaßen aus:

[!code-cpp[NVC_MFCDocView#2](../mfc/codesnippet/cpp/on-update-command-ui-macro_1.h)]

Wie alle Handler, die Funktion zeigt die **Afx_msg** Schlüsselwort. Wie alle Handler zu aktualisieren, nimmt er ein Argument, ein Zeiger auf eine `CCmdUI` Objekt.

## <a name="see-also"></a>Siehe auch

[Vorgehensweise: Aktualisieren von Benutzeroberflächenobjekten](../mfc/how-to-update-user-interface-objects.md)

