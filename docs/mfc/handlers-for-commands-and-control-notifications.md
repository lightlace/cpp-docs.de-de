---
title: "Handler für Befehle und Steuerelementbenachrichtigungen | Microsoft Docs"
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
- commands [MFC], handlers for
- functions [MFC], handler
- handlers [MFC]
- controls [MFC], notifications
- handlers [MFC], control notification [MFC]
- notifications [MFC], handlers for control
- handlers [MFC], command
ms.assetid: 20f57f4a-f577-4c09-80a2-43faf32a1c2e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 748bdd1a2ce6b94a2c935df94de68767ee36875e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="handlers-for-commands-and-control-notifications"></a>Handler für Befehle und Steuerelementbenachrichtigungen
Es sind keine Standardhandler für Befehle oder Steuerelemente-benachrichtigungsmeldungen aus. Aus diesem Grund werden Sie nur gemäß der Konvention in Benennung der Handler für diese Art von Nachrichten gebunden. Wenn Sie den Befehl oder das Steuerelement-Benachrichtigung an einen Handler zuordnen, die Eigenschaftenfenstern schlägt einen Namen basierend auf der Befehls-ID oder Steuerelement-Benachrichtigung Code. Sie können akzeptieren den vorgeschlagenen Namen, ändern oder Ersetzen Sie ihn.  
  
 Konvention schlägt vor, dass Sie Handler in beiden Kategorien für die Benutzeroberfläche Objekt benennen, die sie darstellen. Daher möglicherweise ein Handler für den Befehl "Ausschneiden" im Menü Bearbeiten namens  
  
 [!code-cpp[NVC_MFCMessageHandling#4](../mfc/codesnippet/cpp/handlers-for-commands-and-control-notifications_1.h)]  
  
 Da der Befehl "Ausschneiden" so häufig in Anwendungen implementiert wird, wird das Framework verfügt über vordefinierte die Befehls-ID für den Befehl Cut als **ID_EDIT_CUT**. Eine Liste aller vordefinierten Befehls-IDs finden Sie in der Datei AFXRES. H. Weitere Informationen finden Sie unter [Standardbefehle](../mfc/standard-commands.md).  
  
 Darüber hinaus schlägt Konvention einen Handler für das **BN_CLICKED** Benachrichtigung aus einer Schaltfläche namens "My Button" benannt werden kann  
  
 [!code-cpp[NVC_MFCMessageHandling#5](../mfc/codesnippet/cpp/handlers-for-commands-and-control-notifications_2.h)]  
  
 Sie können mit diesem Befehl ID zuweisen `IDC_MY_BUTTON` , da sie ein Objekt mit anwendungsspezifischen Benutzeroberfläche entspricht.  
  
 Beide Anwendungskategorien Nachrichten akzeptieren keine Argumente und gibt keinen Wert zurück.  
  
## <a name="see-also"></a>Siehe auch  
 [Deklarieren von Meldungshandlerfunktionen](../mfc/declaring-message-handler-functions.md)
