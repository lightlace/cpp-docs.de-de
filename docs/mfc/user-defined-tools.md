---
title: Benutzerdefinierte Tools
ms.date: 11/04/2016
helpviewer_keywords:
- user-defined tools (MFC Extensions)
ms.assetid: cb887421-78ce-4652-bc67-96a53984ccaa
ms.openlocfilehash: 5c5773cdbbd641b30f39494b2d11c282d2d43954
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50607076"
---
# <a name="user-defined-tools"></a>Benutzerdefinierte Tools

MFC unterstützt benutzerdefinierte Tools. Ein benutzerdefiniertes Tool ist ein Befehl für die Inhalte, der eine externe, benutzerdefinierte Anwendung ausgeführt wird. Anpassungsvorgangs können benutzerdefinierte Tools zu verwalten. Jedoch können nicht Sie diesen Prozess verwenden, wenn das Application-Objekt nicht vom abgeleitet wird [CWinAppEx-Klasse](../mfc/reference/cwinappex-class.md). Weitere Informationen zur Anpassung finden Sie unter [Anpassung für MFC](../mfc/customization-for-mfc.md).

Wenn Sie Unterstützung von benutzerdefinierten Tools aktiviert haben, enthält das Dialogfeld "anpassen" automatisch die **Tools** Registerkarte. Die folgende Abbildung zeigt die **Tools** Seite.

![Tools im Dialogfeld "anpassen" Registerkarte](../mfc/media/custdialogboxtoolstab.png "Custdialogboxtoolstab") Anpassung Registerkarte des Dialogfeldes-Tools

## <a name="enabling-user-defined-tools-support"></a>Aktivieren die benutzerdefinierte Unterstützung für tools

Um benutzerdefinierte Tools in einer Anwendung zu aktivieren, rufen [CWinAppEx::EnableUserTools](../mfc/reference/cwinappex-class.md#enableusertools). Allerdings müssen Sie zuerst mehrere Konstanten in den Ressourcendateien Ihrer Anwendung zur Verwendung als Parameter für diesen Aufruf definieren.

Erstellen Sie im Ressourcen-Editor einen dummy-Befehl, der eine entsprechenden Befehls-ID verwendet. Im folgenden Beispiel verwenden wir `ID_TOOLS_ENTRY` als Befehls-ID. Dieses Befehls-ID kennzeichnet einen Speicherort in einen oder mehrere Menüs, in denen das Framework für die benutzerdefinierte Tools eingefügt wird.

In der Zeichenfolgentabelle zur Darstellung der benutzerdefinierten Tools müssen Sie einige aufeinander folgende IDs reserviert. Die Anzahl der Zeichenfolgen, die Sie reserviert ist gleich die maximale Anzahl von Benutzertools, die die Benutzern definieren können. Im folgenden Beispiel wird dies als `ID_USER_TOOL1` über `ID_USER_TOOL10`.

Sie können die Vorschläge für die Benutzer, die Ihnen helfen, wählen Sie die Verzeichnisse und Argumente für die externe Programme, die aufgerufen werden, als Tools anbieten. Zu diesem Zweck erstellen Sie zwei Popupmenüs im Ressourcen-Editor ein. Im folgenden Beispiel wird dies als `IDR_MENU_ARGS` und `IDR_MENU_DIRS`. Definieren Sie für jeden Befehl in diesen Menüs eine Zeichenfolge in der Zeichenfolgentabelle Ihrer Anwendung ein. Die Ressourcen-ID der Zeichenfolge muss mit der Befehls-ID übereinstimmen.

Sie können auch eine abgeleitete Klasse von erstellen [CUserTool-Klasse](../mfc/reference/cusertool-class.md) die standardmäßige Implementierung ersetzen. Übergeben Sie zu diesem Zweck die Runtime-Informationen für die abgeleitete Klasse als vierten Parameter in CWinAppEx::EnableUserTools, anstatt RUNTIME_CLASS ([CUserTool-Klasse](../mfc/reference/cusertool-class.md)).

Nachdem Sie die entsprechenden Konstanten definiert haben, rufen [CWinAppEx::EnableUserTools](../mfc/reference/cwinappex-class.md#enableusertools) benutzerdefinierte Tools zu aktivieren.

Der folgende Methodenaufruf veranschaulicht, wie diese Konstanten:

[!code-cpp[NVC_MFC_VisualStudioDemo#1](../mfc/codesnippet/cpp/user-defined-tools_1.cpp)]

In diesem Beispiel wird auf die Registerkarte "Tools" eingeschlossen werden die **Anpassung** Dialogfeld. Das Framework werden solche Befehle, die die Befehls-ID entspricht ersetzt `ID_TOOLS_ENTRY` in keinem Menü mit den aktuell definierten Benutzertools, wenn ein Benutzer geöffnet wird. Die Befehls-IDs `ID_USER_TOOL1` über `ID_USER_TOOL10` sind für die Verwendung für benutzerdefinierte Tools reserviert. Die Klasse [CUserTool-Klasse](../mfc/reference/cusertool-class.md) behandelt die Aufrufe an die Benutzertools. Der Registerkarte "Tools" die **Anpassung** Dialogfeld enthält Schaltflächen rechts neben der Felder für die Argument- und Verzeichnis, um die Menüs zuzugreifen **IDR_MENU_ARGS** und **IDR_MENU_DIRS**. Wenn ein Benutzer einen Befehl in den Menüs auswählt, fügt das Framework im entsprechenden Textfeld die Zeichenfolge, die die Ressourcen-ID gleich der Befehls-ID.

### <a name="including-predefined-tools"></a>Einschließlich vordefinierter tools

Wenn Sie einige Tools, die beim Start der Anwendung vordefinieren möchten, müssen Sie Sie überschreiben die [CFrameWnd::LoadFrame](../mfc/reference/cframewnd-class.md#loadframe) Methode des Hauptfensters der Anwendung. In dieser Methode müssen Sie die folgenden Schritte ausführen.

##### <a name="to-add-new-tools-in-loadframe"></a>Neue Tools LoadFrame hinzu

1. Abrufen eines Zeigers auf die [CUserToolsManager-Klasse](../mfc/reference/cusertoolsmanager-class.md) Objekt durch Aufrufen von [CWinAppEx::GetUserToolsManager](../mfc/reference/cwinappex-class.md#getusertoolsmanager).

1. Rufen Sie für jedes Tool, das Sie erstellen möchten, [CUserToolsManager::CreateNewTool](../mfc/reference/cusertoolsmanager-class.md#createnewtool). Diese Methode gibt einen Zeiger auf eine [CUserTool-Klasse](../mfc/reference/cusertool-class.md) -Objekt und fügt die neu erstellte Benutzer-Tool zur internen Auflistung von Tools. Wenn Sie die Runtime-Informationen für eine abgeleitete Klasse von bereitgestellt [CUserTool-Klasse](../mfc/reference/cusertool-class.md) als vierten Parameter von [CWinAppEx::EnableUserTools](../mfc/reference/cwinappex-class.md#enableusertools), [CUserToolsManager::CreateNewTool](../mfc/reference/cusertoolsmanager-class.md#createnewtool) instanziiert wird, und geben Sie stattdessen eine Instanz dieser Klasse zurück.

1. Legen Sie für jedes Tool, seine Bezeichnung, indem Sie `CUserTool::m_strLabel` und legen Sie den Befehl durch Aufrufen von `CUserTool::SetCommand`. Die standardmäßige Implementierung des [CUserTool-Klasse](../mfc/reference/cusertool-class.md) übernimmt automatisch die verfügbaren Symbole aus dem Programm, die im Aufruf angegeben wird `SetCommand`.

## <a name="see-also"></a>Siehe auch

[Anpassung für MFC](../mfc/customization-for-mfc.md)<br/>
[CUserTool-Klasse](../mfc/reference/cusertool-class.md)<br/>
[CUserToolsManager-Klasse](../mfc/reference/cusertoolsmanager-class.md)<br/>
[CWinAppEx-Klasse](../mfc/reference/cwinappex-class.md)

