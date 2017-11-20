---
title: Anpassen von Tastatur und Maus | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- customizations [MFC], keyboard and mouse (MFC Extensions)
- keyboard and mouse customizations (MFC Extensions)
ms.assetid: 1f789f1b-5f2e-4b11-b974-e3e2a2e49d82
caps.latest.revision: "23"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 090c74c87810f6c2e7a7641deb248aa97931d93f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="keyboard-and-mouse-customization"></a>Anpassen von Tastatur und Maus
MFC ermöglicht dem Benutzer der Anwendung anpassen, wie es sich um Tastatur- und Mauseingaben behandelt. Der Benutzer kann Tastatureingaben anpassen, indem Sie Befehle Tastenkombinationen zuweisen zu können. Der Benutzer kann die Mauseingabe auch anpassen, indem Sie den Befehl, der ausgeführt werden soll, wenn der Benutzer innerhalb der Anwendung bestimmte Windows doppelklickt auswählen. In diesem Thema wird erläutert, wie die Eingabe für die Anwendung angepasst wird.  
  
 In der **Anpassung** (Dialogfeld), der Benutzer kann die benutzerdefinierten Steuerelemente für die Maus und Tastatur ändern. Um dieses Dialogfeld anzuzeigen, zeigt der Benutzer auf **anpassen** auf die **Ansicht** Menü und klickt dann auf **Symbolleisten und Andocken**. Klicken Sie im Dialogfeld klickt der Benutzer entweder der **Tastatur** Registerkarte oder die **Maus** Registerkarte.  
  
## <a name="keyboard-customization"></a>Anpassung der Tastatur  
 Die folgende Abbildung zeigt die **Tastatur** auf der Registerkarte die **Anpassung** (Dialogfeld).  
  
 ![Registerkarte "Tastatur" im Dialogfeld "anpassen"](../mfc/media/mfcnextkeyboardtab.png "Mfcnextkeyboardtab")  
Registerkarte "Anpassung" Tastatur  
  
 Der Benutzer interagiert mit der Registerkarte "Tastatur" eine oder mehrere Tastenkombinationen einem Befehl zugewiesen. Die verfügbaren Befehle sind auf der linken Seite der Registerkarte aufgeführt. Der Benutzer kann einen der verfügbaren Befehle im Menü auswählen. Nur Befehle im Menü können eine Tastenkombination zugeordnet werden. Nachdem der Benutzer eine neue Verknüpfung gibt die **zuweisen** Schaltfläche aktiviert wird. Wenn der Benutzer auf diese Schaltfläche klickt, ordnet der Anwendung den ausgewählten Befehl diese Tastenkombination.  
  
 Alle von der aktuell zugewiesenen Tastenkombinationen werden im Listenfeld in der rechten Spalte aufgeführt. Der Benutzer kann auch einzelne Verknüpfungen auswählen und entfernen Sie diese oder setzen Sie alle Zuordnungen für die Anwendung zurück.  
  
 Wenn Sie diese Anpassung in Ihrer Anwendung unterstützen möchten, müssen Sie erstellen eine [CKeyboardManager](../mfc/reference/ckeyboardmanager-class.md) Objekt. Zum Erstellen einer `CKeyboardManager` Objekt, rufen Sie die Funktion [CWinAppEx::InitKeyboardManager](../mfc/reference/cwinappex-class.md#initkeyboardmanager). Diese Methode erstellt und initialisiert einen Tastatur-Manager. Wenn Sie eine Tastatur Manager manuell erstellen, noch müssen Sie aufrufen `CWinAppEx::InitKeyboardManager` initialisiert werden.  
  
 Wenn Sie den Assistenten zum Erstellen Ihrer Anwendung verwenden, wird der Assistent die Tastatur-Manager initialisiert. Nachdem Ihre Anwendung über die Tastatur-Manager initialisiert, fügt das Framework eine **Tastatur** die Registerkarte der **Anpassung** (Dialogfeld).  
  
## <a name="mouse-customization"></a>Anpassung für Maus  
 Die folgende Abbildung zeigt die **Maus** auf der Registerkarte die **Anpassung** (Dialogfeld).  
  
 ![Registerkarte "Maus" im Dialogfeld "anpassen"](../mfc/media/mfcnextmousetab.png "Mfcnextmousetab")  
Registerkarte "Anpassung" Maus  
  
 Der Benutzer mit dieser Registerkarte können Sie ein Menü zuweisen interagiert Befehl aus, um die Maus, doppelklicken Sie auf Aktion. Der Benutzer wählt eine Sicht aus der linken Seite des Fensters und verwendet dann die Steuerelemente auf der rechten Seite, um einen Befehl mit der Doppelklickaktion durch zuordnen. Nachdem der Benutzer klickt auf die **schließen**, die Anwendung den zugeordneten Befehl ausführt, wenn der Benutzer auf eine beliebige Stelle in der Ansicht doppelklickt.  
  
 Maus Anpassung ist standardmäßig nicht aktiviert, wenn Sie eine Anwendung mithilfe des Assistenten zum Erstellen.  
  
#### <a name="to-enable-mouse-customization"></a>So aktivieren Sie die Maus Anpassung  
  
1.  Initialisieren einer [CMouseManager](../mfc/reference/cmousemanager-class.md) Objekt durch Aufrufen von [CWinAppEx::InitMouseManager](../mfc/reference/cwinappex-class.md#initmousemanager).  
  
2.  Rufen Sie einen Zeiger auf die Maus-Manager mithilfe [CWinAppEx::GetMouseManager](../mfc/reference/cwinappex-class.md#getmousemanager).  
  
3.  Ansichten der Maus-Manager hinzufügen, mit der [CMouseManager::AddView](../mfc/reference/cmousemanager-class.md#addview) Methode. Dies gilt für jede Ansicht der Maus-Manager hinzufügen möchten.  
  
 Nachdem die Anwendung die Maus Manager initialisiert, fügt das Framework der **Maus** die Registerkarte der **anpassen** (Dialogfeld). Wenn Sie keine Ansichten hinzufügen, verursacht der Zugriff auf die Registerkarte "eine nicht behandelte Ausnahme aus. Nach der Erstellung einer Liste der Ansichten, die **Maus** Registerkarte für den Benutzer verfügbar ist.  
  
 Wenn Sie eine neue Ansicht der Maus-Manager hinzufügen, weisen Sie dieser eine eindeutige ID. Wenn Sie die Maus Anpassung für ein Fenster unterstützen möchten, müssen Sie verarbeiten die `WM_LBUTTONDBLCLICK` Nachricht und rufen die [CWinAppEx::OnViewDoubleClick](../mfc/reference/cwinappex-class.md#onviewdoubleclick) Funktion. Wenn Sie diese Funktion aufrufen, ist einer der Parameter die ID für dieses Fensters. Es ist der Verantwortung des Programmierers zum Nachverfolgen der ID-Nummern und die ihnen zugeordneten Objekte.  
  
## <a name="security-concerns"></a>Sicherheitsaspekte  
 Wie in beschrieben [benutzerdefinierte Tools](../mfc/user-defined-tools.md), die Benutzer kann das Doppelklickereignis benutzerdefiniertes Tool-ID zuordnen. Wenn der Benutzer eine Ansicht doppelklickt, sucht die Anwendung ein Tool, das die zugeordneten-ID übereinstimmt. Wenn die Anwendung ein übereinstimmendes Tool gefunden wird, führt er das Tool an. Wenn die Anwendung ein entsprechendes Tool finden kann, wird eine WM_COMMAND-Nachricht mit der ID auf die Ansicht, die doppelgeklickt wurde gesendet.  
  
 Die angepassten Einstellungen werden in der Registrierung gespeichert. Durch Bearbeiten der Registrierung, kann ein Angreifer eine gültige Benutzer-ID-Tool durch ein beliebiger Befehl ersetzen. Wenn der Benutzer eine Ansicht doppelklickt, verarbeitet die Sicht des Befehls, der der Angreifer bepflanzt an. Dies kann zu unerwarteten und möglicherweise gefährliches Verhalten verursachen.  
  
 Darüber hinaus kann diese Art von Angriff Benutzer Schnittstelle Schutzvorrichtungen umgangen werden. Angenommen Sie, dass eine Anwendung drucken deaktiviert wurde. D. h. in der Benutzeroberfläche der **Drucken** Menüs und Schaltflächen sind nicht verfügbar. Normalerweise wird verhindert, dass dies die Anwendung am drucken. Jedoch wenn ein Angreifer die Registrierung bearbeitet, ein Benutzer kann jetzt konnte gesendet werden den Druckbefehl direkt durch Doppelklicken auf die Sicht umgehen die Elemente der Benutzeroberfläche, die nicht zur Verfügung stehen.  
  
 Zum Schutz gegen diese Art von Angriff fügen Sie Code Ihrer Anwendung Befehlshandler, um sicherzustellen, dass ein Befehl gültig ist, bevor er ausgeführt wird. Richten Sie sich nicht auf der Benutzeroberfläche, um zu verhindern, dass einen Befehl für die Anwendung gesendet werden.  
  
## <a name="see-also"></a>Siehe auch  
 [Anpassung für MFC](../mfc/customization-for-mfc.md)   
 [CKeyboardManager-Klasse](../mfc/reference/ckeyboardmanager-class.md)   
 [CMouseManager-Klasse](../mfc/reference/cmousemanager-class.md)   
 [Sicherheitsauswirkungen der Anpassung](../mfc/security-implications-of-customization.md)

