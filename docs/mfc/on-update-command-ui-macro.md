---
title: ON_UPDATE_COMMAND_UI Macro
ms.date: 09/06/2019
f1_keywords:
- ON_UPDATE_COMMAND_UI
helpviewer_keywords:
- ON_UPDATE_COMMAND_UI macro [MFC]
- update handlers [MFC]
- command-handler macros
- updating user-interface objects [MFC]
ms.assetid: 3e72b50f-4119-4c82-81cf-6e09b132de05
ms.openlocfilehash: 2a3f097a44e96fc470719ce636cc1b73e676fb38
ms.sourcegitcommit: 2f96e2fda591d7b1b28842b2ea24e6297bcc3622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2019
ms.locfileid: "71095849"
---
# <a name="on_update_command_ui-macro"></a>ON_UPDATE_COMMAND_UI Macro

Öffnen Sie **Klassenansicht**, und klicken Sie dann mit der rechten Maustaste auf die Klasse, der der Handler hinzugefügt wird, und wählen Sie den **Klassen-Assistenten**aus, um ein Benutzeroberflächen Objekt mit einem Befehls Aktualisierungs Handler in einem Befehls Zielobjekt zu verbinden. Suchen Sie die ID des Benutzeroberflächen Objekts in der Liste auf der linken Seite, wählen Sie dann im rechten Bereich **UPDATE_COMMAND_UI** aus, und klicken Sie auf **Handler hinzufügen**. Dadurch wird eine Handlerfunktion in der-Klasse erstellt und der entsprechende Eintrag in der Meldungs Zuordnung hinzugefügt. Weitere Informationen finden [Sie unter Mapping messages to Functions](../mfc/reference/mapping-messages-to-functions.md) . Sie können zusätzliche Nachrichten angeben, die im Bereich **Meldungen** verarbeitet werden sollen.

Um z. b. den Befehl Clear All im Menü Bearbeiten des Programms zu aktualisieren, verwenden Sie den **Klassen-Assistenten** , um einen Meldungs Zuordnungs Eintrag in der ausgewählten Klasse hinzuzufügen, eine Funktionsdeklaration `OnUpdateEditClearAll` für einen Befehls Aktualisierungs Handler, der in der Klassen Deklaration aufgerufen wird, und einen leeren Funktions Vorlage in der Implementierungs Datei der Klasse. Der Funktionsprototyp sieht wie folgt aus:

[!code-cpp[NVC_MFCDocView#2](../mfc/codesnippet/cpp/on-update-command-ui-macro_1.h)]

Wie bei allen Handlern zeigt die Funktionsdeklaration das **afx_msg** -Schlüsselwort an. Wie bei allen Update Handlern benötigt es ein Argument, einen Zeiger auf ein `CCmdUI` -Objekt.

## <a name="see-also"></a>Siehe auch

[Vorgehensweise: Aktualisieren von Benutzeroberflächenobjekten](../mfc/how-to-update-user-interface-objects.md)
