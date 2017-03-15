---
title: "Anpassen von Tastatur und Maus | Microsoft Docs"
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
  - "Anpassungen, Tastatur und Maus (MFC-Erweiterungen)"
  - "Tastatur und Maus Anpassungen (MFC-Erweiterungen)"
ms.assetid: 1f789f1b-5f2e-4b11-b974-e3e2a2e49d82
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 19
---
# Anpassen von Tastatur und Maus
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC können die Benutzer der Anwendung, anzupassen, z es Tastatur\- und Mauseingabe behandelt.  Der Benutzer kann Tastatureingabe anpassen, indem Sie Tastenkombinationen an Befehle zuweist.  Der Benutzer kann die Mauseingabe auch anpassen, indem Sie den Befehl auswählt, der ausgeführt werden soll, wenn der Benutzer in bestimmten Fenster der Anwendung auf.  In diesem Thema wird erläutert, wie die Eingabe für die Anwendung anpassen.  
  
 Im Dialogfeld **Anpassung** kann der Benutzer die benutzerdefinierten Steuerelemente für die Maus und die Tastatur ändern.  Um dieses Dialogfeld anzuzeigen, klickt die Benutzerpunkte zu **Anpassen** im Menü **Ansicht** und dann auf **Symbolleisten und Andocken**.  Im Dialogfeld klickt der Benutzer auf die Registerkarte **Tastatur** oder auf die Registerkarte **Maus**.  
  
## Tastatur\-Anpassung  
 Die folgende Abbildung zeigt die Registerkarte **Tastatur** des Dialogfelds **Anpassung** an.  
  
 ![Registerkarte "Tastatur" im Dialogfeld "Anpassen"](../mfc/media/mfcnextkeyboardtab.png "MFCNextKeyboardTab")  
Tastatur\-Anpassungs\-Registerkarte  
  
 Der Benutzer interagiert mit der Tastaturregisterkarte ein, um eine oder mehrere Tastenkombinationen einen Befehl zuweisen.  Die verfügbaren Befehle werden auf der linken Seite der Registerkarte aufgeführt.  Der Benutzer kann jeden verfügbaren Befehl im Menü auswählen.  Nur Menübefehle können mit einer Tastenkombination zugeordnet werden.  Nachdem der Benutzer eine neue Verknüpfung eingibt, wird die Schaltfläche **Zuweisen** aktiviert.  Wenn der Benutzer auf diese Schaltfläche klickt, wird die Anwendung den ausgewählten Befehl mit dieser Bindung zu.  
  
 Alle derzeit zugewiesenen Tastenkombinationen werden im Listenfeld in der rechten Spalte aufgeführten.  Der Benutzer kann einzelne auch Tastenkombinationen auswählen und diese entfernen oder alle Zuordnungen für die Anwendung wiederherstellen.  
  
 Wenn Sie diese Anpassung in der Anwendung unterstützen möchten, müssen Sie ein [CKeyboardManager](../mfc/reference/ckeyboardmanager-class.md)\-Objekt erstellen.  Um ein `CKeyboardManager`\-Objekt zu erstellen, rufen Sie die [CWinAppEx::InitKeyboardManager](../Topic/CWinAppEx::InitKeyboardManager.md) auf.  Diese Methode erstellt und initialisiert einen Tastaturmanager.  Wenn Sie einen Tastaturmanager manuell erstellen, müssen Sie `CWinAppEx::InitKeyboardManager` erneut aufrufen, um es zu initialisieren.  
  
 Wenn Sie den Assistenten verwenden, um die Anwendung zu erstellen, initialisiert der Assistent den Tastaturmanager.  Nachdem die Anwendung den Tastaturmanager initialisiert, fügt das Framework einer Registerkarte **Tastatur** dem Dialogfeld **Anpassung** hinzu.  
  
## Maus\-Anpassung  
 Die folgende Abbildung zeigt die Registerkarte **Maus** des Dialogfelds **Anpassung** an.  
  
 ![Registerkarte "Maus" im Dialogfeld "Anpassen"](../mfc/media/mfcnextmousetab.png "MFCNextMouseTab")  
Maus\-Anpassungs\-Registerkarte  
  
 Der Benutzer interagiert diese Registerkarte ein, um einen Menübefehl zur Mausdoppelklickaktion zuzuweisen.  Der Benutzer wählt eine Ansicht von der linken Seite des Fensters aus und anschließend die Steuerelemente auf der rechten Seite, um einen Befehl mit der Doppelklickaktion zuzuordnen.  Nachdem der Benutzer auf **Schließen** klickt, führt die Anwendung den zugeordneten Befehl aus, wenn der Benutzer auf eine beliebige Stelle in der Ansicht doppelklickt.  
  
 Standardmäßig wird Mausanpassung nicht aktiviert, wenn Sie eine Anwendung erstellen, indem Sie den Assistenten verwenden.  
  
#### So Mausanpassung aktivieren  
  
1.  Initialisieren Sie ein [CMouseManager](../mfc/reference/cmousemanager-class.md)\-Objekt, indem Sie [CWinAppEx::InitMouseManager](../Topic/CWinAppEx::InitMouseManager.md) aufrufen.  
  
2.  Rufen Sie einen Zeiger auf das Mausmanager, indem Sie [CWinAppEx::GetMouseManager](../Topic/CWinAppEx::GetMouseManager.md) verwenden.  
  
3.  Fügen Sie dem Mausmanager Ansichten hinzu, indem Sie die [CMouseManager::AddView](../Topic/CMouseManager::AddView.md)\-Methode.  Vorgehensweise für jede Ansicht, die Sie dem Mausmanager hinzufügen möchten.  
  
 Nachdem die Anwendung den Mausmanager initialisiert, fügt das Framework der Registerkarte **Maus** dem Dialogfeld **Anpassen** hinzu.  Wenn Sie keine Ansichten hinzufügen, verursacht das Zugreifen auf die Registerkarte einen Ausnahme.  Nachdem Sie eine Liste von Ansichten erstellt haben, wird die Registerkarte **Maus** dem Benutzer zur Verfügung.  
  
 Wenn Sie eine neue Ansicht dem Mausmanager hinzufügen, geben Sie eine eindeutige ID  Wenn Sie Mausanpassung für ein Fenster unterstützen möchten, müssen Sie `WM_LBUTTONDBLCLICK` die Meldung verarbeiten und die [CWinAppEx::OnViewDoubleClick](../Topic/CWinAppEx::OnViewDoubleClick.md)\-Funktion aufrufen.  Wenn Sie diese Funktion aufrufen, ist einer der Parameter für die ID dieses Fenster.  Es liegt in der Verantwortung des Programmierers, die ID\-Nummern und Objekte zu verfolgen, die ihnen zugeordnete werden.  
  
## Sicherheitsaspekte  
 Wie in [Benutzerdefinierte Tools](../mfc/user-defined-tools.md) beschrieben, können Benutzer eine benutzerdefinierte ID Tool mit dem Doppelklickereignis zuordnen.  Wenn der Benutzer auf eine Ansicht doppelklickt, sucht die Anwendung nach einem Benutzertool, das die zugeordnete ID übereinstimmt  Wenn die Anwendung ein entsprechendes Tool findet, werden das Tool aus.  Wenn die Anwendung ein entsprechendes Tool nicht finden kann, sendet sie einer WM\_COMMAND\-Meldung mit ID die Ansicht, die doppelt geklickt wurde.  
  
 Die benutzerdefinierten Einstellungen werden in der Registrierung gespeichert.  Durch die Registrierung hat, kann ein Angreifer eine ID Tool des gültigen Benutzers durch einen beliebigen Befehl ersetzen.  Wenn der Benutzer auf eine Ansicht doppelklickt, verarbeitet die Ansicht den Befehl, den der Angreifer pflanzte.  Dies könnte zu unerwartetem und möglicherweise gefährliches Verhalten führen.  
  
 Darüber hinaus kann diese Art von Angriffen Benutzeroberflächenschutz umgehen.  Angenommen, eine Anwendung den deaktivierten Drucken hat.  Das heißt, in der Benutzeroberfläche, sind das Menü **Drucken** und die Schaltfläche ist nicht verfügbar.  Normalerweise verhindert dieses die Anwendung am Drucken.  Aber, wenn ein Angreifer die Registrierung hat, kann ein Benutzer kann den Druckbefehl jetzt direkt senden, indem er auf die Ansicht doppelt geklickt hat und Benutzeroberflächenelemente umgangen, die nicht verfügbar sind.  
  
 Um vor dieser Art von Angriffen zu schützen, fügen Sie dem Code Anwendungsbefehlshandler hinzu ob ein Befehl gültig ist vor dessen Ausführung.  Hängen Sie nicht von der Benutzeroberfläche ab, um einen Befehl an die Anwendung gesendet werden.  
  
## Siehe auch  
 [Anpassung für MFC](../mfc/customization-for-mfc.md)   
 [CKeyboardManager Class](../mfc/reference/ckeyboardmanager-class.md)   
 [CMouseManager Class](../mfc/reference/cmousemanager-class.md)   
 [Sicherheitsauswirkungen der Anpassung](../mfc/security-implications-of-customization.md)