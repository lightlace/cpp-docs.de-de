---
title: "Benutzerdefinierte Tools | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Benutzerdefinierte Tools (MFC-Erweiterungen)"
ms.assetid: cb887421-78ce-4652-bc67-96a53984ccaa
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# Benutzerdefinierte Tools
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC unterstützt benutzerdefinierte Tools.  Ein benutzerdefiniertes Tool ist ein spezieller Befehl, der ein externes, vom Benutzer angegebenes Programm ausführen.  Sie können den Anpassungsprozess verwenden, um benutzerdefinierte Tools zu verwalten.  Sie können diesen Prozess nicht verwenden, wenn das Anwendungsobjekt nicht von [CWinAppEx Class](../mfc/reference/cwinappex-class.md) abgeleitet wird.  Weitere Informationen zur Anpassung, finden Sie unter [Anpassung für MFC](../mfc/customization-for-mfc.md).  
  
 Wenn Sie benutzerdefinierte Tools haben, schließt das Anpassungsdialogfeld automatisch die Registerkarte **Tools** ein.  Die folgende Abbildung zeigt die Seite **Tools** an.  
  
 ![Registerkarte "Extras" im Dialogfeld "Anpassen"](../mfc/media/custdialogboxtoolstab.png "CustDialogBoxToolsTab")  
Anpassungsdialogfeld Toolregisterkarte  
  
## Aktivieren der benutzerdefinierten Tools  
 Um benutzerdefinierte Tools in einer Anwendung zu ermöglichen, rufen Sie [CWinAppEx::EnableUserTools](../Topic/CWinAppEx::EnableUserTools.md) auf.  Sie müssen jedoch mehrere Konstanten in den Ressourcendateien der Anwendung zuerst definieren, als Parameter für den Aufruf zu verwenden.  
  
 Im Ressourcen\-Editor erstellen Sie einen Befehl einem Dummy\-, der ID eine entsprechende Befehl verwendet  Im folgenden Beispiel verwenden Sie **ID\_TOOLS\_ENTRY**  als Befehl ID  Diese Befehls\-ID markiert einen Speicherort in einen oder mehreren Menüs, in dem das Framework die benutzerdefinierten Tools ein.  
  
 Sie müssen einige nachfolgende IDs in der Zeichenfolgentabelle zurückstellen, um die benutzerdefinierten Tools darzustellen.  Die Anzahl von Zeichenfolgen, die Sie zurückstellen, entspricht die maximale Anzahl Benutzertools, die die Benutzer definieren können.  Im folgenden Beispiel werden diese **ID\_USER\_TOOL1** durch **ID\_USER\_TOOL10**.  
  
 Sie können die Vorschläge Benutzern bereitstellen, das beim Diskutieren, Verzeichnisse und Argumente für die externe Programme auszuwählen, die mit Tools aufgerufen werden.  Hierzu, erstellen Sie zwei Popupmenüs im Ressourcen\-Editor.  Im folgenden Beispiel werden diese **IDR\_MENU\_ARGS** und **IDR\_MENU\_DIRS**.  Für jeden Befehl in den Menüs, definieren Sie eine Zeichenfolge in der Anwendungszeichenfolgentabelle.  Die Ressourcen\-ID der Zeichenfolge muss gleich der Befehl ID sein  
  
 Sie können eine abgeleitete Klasse von [CUserTool Class](../mfc/reference/cusertool-class.md) auch erstellen, um die Standardimplementierung zu ersetzen.  Hierzu, übergeben Sie die Laufzeitinformationen für die abgeleitete Klasse als der vierte Parameter in CWinAppEx::EnableUserTools, anstelle RUNTIME\_CLASS \([CUserTool Class](../mfc/reference/cusertool-class.md)\).  
  
 Nachdem Sie die erforderlichen Konstanten definieren, rufen Sie [CWinAppEx::EnableUserTools](../Topic/CWinAppEx::EnableUserTools.md), um aus benutzerdefinierten Tools zu aktivieren.  
  
 Der folgenden Methodenaufruf veranschaulicht, wie diese Konstanten verwendet:  
  
 [!CODE [NVC_MFC_VisualStudioDemo#1](../CodeSnippet/VS_Snippets_Misc/NVC_MFC_VisualStudioDemo#1)]  
  
 In diesem Beispiel wird die Toolregisterkarte im Dialogfeld **Anpassung** enthalten.  Das Framework ersetzt jeden Befehl, der die Befehls\-ID **ID\_TOOLS\_ENTRY** in einem Menü mit dem Satz des momentan definierten Benutzers verarbeitet, wenn ein Benutzer das Menü geöffnet wird.  Die Befehls\-IDs **ID\_USER\_TOOL1** von **ID\_USER\_TOOL10** werden zur Verwendung für benutzerdefinierte Tools reserviert.  Die [CUserTool Class](../mfc/reference/cusertool-class.md) verarbeitet Aufrufe die Benutzertools.  Die Toolregisterkarte des Dialogfelds **Anpassung** stellt Schaltflächen auf der rechten Seite der Verzeichniseingabefelder Argument\- und bereit, um auf die Menüs **IDR\_MENU\_ARGS** und **IDR\_MENU\_DIRS** zuzugreifen., wenn ein Benutzer einen Befehl aus einem dieser Menüs auswählen, dem Framework fügt zum entsprechenden Textfeld die Zeichenfolge, die die Ressourcen\-ID gleich der Befehl ID verfügt  
  
### Durch vordefinierte Tools  
 Wenn Sie mehrere Tools auf dem Anwendungsstart vordefinieren möchten, müssen Sie die Methode [CFrameWnd::LoadFrame](../Topic/CFrameWnd::LoadFrame.md) des Hauptfensters der Anwendung überschrieben.  In dieser Methode müssen Sie die folgenden Schritte ausführen.  
  
##### So neuen Tools in LoadFrame hinzufügen  
  
1.  Rufen Sie einen Zeiger auf das [CUserToolsManager Class](../mfc/reference/cusertoolsmanager-class.md)\-Objekt, indem Sie [CWinAppEx::GetUserToolsManager](../Topic/CWinAppEx::GetUserToolsManager.md) aufrufen.  
  
2.  Für jedes Tool, das Sie erstellen möchten, rufen Sie [CUserToolsManager::CreateNewTool](../Topic/CUserToolsManager::CreateNewTool.md).  Diese Methode gibt einen Zeiger auf ein [CUserTool Class](../mfc/reference/cusertool-class.md)\-Objekt zurück und fügt dem neu erstellten Benutzertool der internen Auflistung der Tools hinzugefügt.  Wenn Sie die Laufzeitinformationen für eine abgeleitete Klasse [CUserTool Class](../mfc/reference/cusertool-class.md) als vierte Parameter von [CWinAppEx::EnableUserTools](../Topic/CWinAppEx::EnableUserTools.md) bereitgestellt haben, instanziiert [CUserToolsManager::CreateNewTool](../Topic/CUserToolsManager::CreateNewTool.md) und gibt eine Instanz dieser Klasse stattdessen zurück.  
  
3.  Für jedes Tool Festlegen seiner Beschriftung, indem Sie `CUserTool::m_strLabel` festlegen fest und den Befehl fest, indem Sie `CUserTool::SetCommand` aufgerufen haben.  Die Standardimplementierung von [CUserTool Class](../mfc/reference/cusertool-class.md) wird automatisch verfügbaren Symbole vom Programm ab, das im Aufruf von `SetCommand` angegeben wird.  
  
## Siehe auch  
 [Anpassung für MFC](../mfc/customization-for-mfc.md)   
 [CUserTool Class](../mfc/reference/cusertool-class.md)   
 [CUserToolsManager Class](../mfc/reference/cusertoolsmanager-class.md)   
 [CWinAppEx Class](../mfc/reference/cwinappex-class.md)