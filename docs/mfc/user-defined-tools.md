---
title: Benutzerdefinierte Tools | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- user-defined tools (MFC Extensions)
ms.assetid: cb887421-78ce-4652-bc67-96a53984ccaa
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 17f0751a2cb3f78730ec948d737dc99b85c2e735
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="user-defined-tools"></a>Benutzerdefinierte Tools
MFC unterstützt benutzerdefinierte Tools. Ein benutzerdefiniertes Tool ist eine spezielle Befehl, der eine externe, benutzerdefinierte Anwendung ausgeführt wird. Anpassungsvorgangs können Sie benutzerdefinierte Tools verwalten. Allerdings können Sie diesen Prozess verwenden, wenn Anwendungsobjekts nicht abgeleitet ist [CWinAppEx Class](../mfc/reference/cwinappex-class.md). Weitere Informationen zur Anpassung finden Sie unter [Anpassung für MFC](../mfc/customization-for-mfc.md).  
  
 Wenn Sie Unterstützung von benutzerdefinierten Tools aktiviert haben, enthält das Dialogfeld "Anpassung" automatisch die **Tools** Registerkarte. Die folgende Abbildung zeigt die **Tools** Seite.  
  
 ![Tools Registerkarte im Dialogfeld "anpassen"](../mfc/media/custdialogboxtoolstab.png "Custdialogboxtoolstab")  
Registerkarte "Extras" Anpassung Dialogfeld-Feld  
  
## <a name="enabling-user-defined-tools-support"></a>Aktivieren von benutzerdefinierten tools unterstützen  
 Um eine benutzerdefinierte Tools in einer Anwendung zu aktivieren, rufen [CWinAppEx::EnableUserTools](../mfc/reference/cwinappex-class.md#enableusertools). Allerdings müssen Sie zunächst einige Konstanten in den Ressourcendateien Ihrer Anwendung zur Verwendung als Parameter für diesen Aufruf definieren.  
  
 Erstellen Sie im Ressourcen-Editor einen dummy-Befehl, der eine entsprechenden Befehl-ID verwendet. Im folgenden Beispiel verwenden wir **ID_TOOLS_ENTRY** als die Befehls-ID. Dieses Befehls-ID kennzeichnet eine Position in einen oder mehrere Menüs, in dem das Framework für die benutzerdefinierte Tools eingefügt wird.  
  
 In der Zeichenfolgentabelle zur Darstellung der benutzerdefinierten Tools müssen Sie einige aufeinander folgende IDs reserviert. Die Anzahl von Zeichenfolgen, die Sie zur Seite gedrängt festlegen, entspricht die maximale Anzahl von Benutzertools, mit denen die Benutzer definieren können. Im folgenden Beispiel werden diese benannt **ID_USER_TOOL1** über **ID_USER_TOOL10**.  
  
 Sie können Vorschläge für die Benutzer, die Ihnen helfen, die Verzeichnisse und Argumente für externe Programme, die aufgerufen werden, wie Verwaltungstools auswählen. Zu diesem Zweck erstellen Sie zwei Popupmenüs im Ressourcen-Editor. Im folgenden Beispiel wird diese mit dem Namen **IDR_MENU_ARGS** und **IDR_MENU_DIRS**. Definieren Sie für jeden Befehl in diesen Menüs eine Zeichenfolge in der Zeichenfolgentabelle Ihrer Anwendung ein. Die Ressourcen-ID der Zeichenfolge muss die Befehls-ID. gleich sein.  
  
 Sie können auch eine abgeleitete Klasse von erstellen [CUserTool Klasse](../mfc/reference/cusertool-class.md) die standardmäßige Implementierung ersetzen. Übergeben Sie zu diesem Zweck die Laufzeitinformationen für die abgeleitete Klasse als vierten Parameter in CWinAppEx::EnableUserTools, anstatt RUNTIME_CLASS ([CUserTool Klasse](../mfc/reference/cusertool-class.md)).  
  
 Nachdem Sie die entsprechenden Konstanten definiert haben, rufen [CWinAppEx::EnableUserTools](../mfc/reference/cwinappex-class.md#enableusertools) benutzerdefinierte Tools zu aktivieren.  
  
 Der folgende Methodenaufruf zeigt, wie diese Konstanten:  
  
 [!code-cpp[NVC_MFC_VisualStudioDemo#1](../mfc/codesnippet/cpp/user-defined-tools_1.cpp)]  
  
 In diesem Beispiel wird die Registerkarte "Extras" auf enthalten die **Anpassung** (Dialogfeld). Das Framework werden solche Befehle, die die Befehls-ID entspricht ersetzt **ID_TOOLS_ENTRY** in keinem Menü mit den aktuell definierten Benutzertools, sobald ein Benutzer das Menü geöffnet wird. Die Befehls-IDs **ID_USER_TOOL1** über **ID_USER_TOOL10** sind für die Verwendung von benutzerdefinierten Tools reserviert. Die Klasse [CUserTool Klasse](../mfc/reference/cusertool-class.md) Aufrufe an die Benutzertools verarbeitet. Der Registerkarte "Tools" der **Anpassung** Dialogfeld stellt Schaltflächen rechts neben die Argument- und Directory Felder auf die Menüs **IDR_MENU_ARGS** und **IDR_MENU_DIRS**. Wenn ein Benutzer einen Befehl von einem mithilfe dieser Menüs auswählt, fügt das Framework an das entsprechende Textfeld die Zeichenfolge, die die Ressourcen-ID gleich die Befehls-ID.  
  
### <a name="including-predefined-tools"></a>Vordefinierten Tools einschließlich  
 Einige Tools auf den Start der Anwendung vordefinieren werden sollen, müssen Sie überschreiben die [CFrameWnd::LoadFrame](../mfc/reference/cframewnd-class.md#loadframe) Methode des Hauptfensters der Anwendung. In dieser Methode müssen Sie die folgenden Schritte ausführen.  
  
##### <a name="to-add-new-tools-in-loadframe"></a>Neue Tools in LoadFrame hinzu  
  
1.  Abrufen eines Zeigers auf die [CUserToolsManager Klasse](../mfc/reference/cusertoolsmanager-class.md) Objekt durch Aufrufen von [CWinAppEx::GetUserToolsManager](../mfc/reference/cwinappex-class.md#getusertoolsmanager).  
  
2.  Rufen Sie für jedes Tool, das Sie erstellen möchten, [CUserToolsManager::CreateNewTool](../mfc/reference/cusertoolsmanager-class.md#createnewtool). Diese Methode gibt einen Zeiger auf eine [CUserTool Klasse](../mfc/reference/cusertool-class.md) -Objekt und fügt die neu erstellte benutzertool zur internen Auflistung von Tools. Wenn Sie die Laufzeitinformationen für eine abgeleitete Klasse von bereitgestellt [CUserTool Klasse](../mfc/reference/cusertool-class.md) als der vierte Parameter der [CWinAppEx::EnableUserTools](../mfc/reference/cwinappex-class.md#enableusertools), [CUserToolsManager::CreateNewTool](../mfc/reference/cusertoolsmanager-class.md#createnewtool) instanziiert wird, und geben Sie stattdessen eine Instanz dieser Klasse zurück.  
  
3.  Legen Sie für jedes Tool, seine Bezeichnung, indem Sie `CUserTool::m_strLabel` und legen Sie den Befehl durch Aufrufen von `CUserTool::SetCommand`. Die standardmäßige Implementierung des [CUserTool Klasse](../mfc/reference/cusertool-class.md) übernimmt verfügbaren Symbole aus der Anwendung, die im Aufruf angegeben wird `SetCommand`.  
  
## <a name="see-also"></a>Siehe auch  
 [Anpassung für MFC](../mfc/customization-for-mfc.md)   
 [CUserTool-Klasse](../mfc/reference/cusertool-class.md)   
 [CUserToolsManager-Klasse](../mfc/reference/cusertoolsmanager-class.md)   
 [CWinAppEx-Klasse](../mfc/reference/cwinappex-class.md)




