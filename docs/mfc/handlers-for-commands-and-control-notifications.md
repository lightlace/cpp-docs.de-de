---
title: "Handler f&#252;r Befehle und Steuerelementbenachrichtigungen"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Befehle, Handler für"
  - "Steuerelemente [MFC], Benachrichtigungen"
  - "Funktionen [C++], Handler"
  - "Handler"
  - "Handler, Befehl"
  - "Handler, Steuerelementebenachrichtigung"
  - "Benachrichtigungen, Handler für Steuerelemente"
ms.assetid: 20f57f4a-f577-4c09-80a2-43faf32a1c2e
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Handler f&#252;r Befehle und Steuerelementbenachrichtigungen
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Es gibt keine standardmäßige Handler für Befehle oder Steuerelement\-Benachrichtigungen.  Daher werden Sie nur als gebunden, wenn die Handler für diese Kategorien von Meldungen benennt.  Wenn Sie den Befehl oder der Steuerelementbenachrichtigung einem Handler zuordnen, schlägt die Eigenschaftenfenster einen Namen auf dem Befehls\-ID\- oder Steuerelementbenachrichtigungscode vor.  Sie können den vorgeschlagenen Namen akzeptiert, diesen ändern oder diesen ersetzen.  
  
 Konvention schlägt vor, dass Sie Handler in beiden Kategorien für die Benutzeroberflächeobjekt benennen, die diese darstellen.  Demnach würde ein Handler für den Befehl Ausschneiden im Menü Bearbeiten Namen möglicherweise  
  
 [!CODE [NVC_MFCMessageHandling#4](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCMessageHandling#4)]  
  
 Da der Befehl Ausschneiden so häufig in Anwendungen implementiert wird, definiert das Framework die Befehls\-ID für den Befehl Ausschneiden als **ID\_EDIT\_CUT** vor.  Eine Liste aller vordefinierten Befehls\-IDs, finden Sie die Datei AFXRES.H.  Weitere Informationen finden Sie unter [Standardbefehle](../mfc/standard-commands.md).  
  
 Außerdem schlägt Konvention vor, dass ein Handler kann **BN\_CLICKED** für die Benachrichtigung von einer Schaltfläche, die "My Schaltfläche" bezeichnete, würde mit  
  
 [!CODE [NVC_MFCMessageHandling#5](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCMessageHandling#5)]  
  
 Sie können möglicherweise diesem Befehl die ID `IDC_MY_BUTTON` zu, da sie auf ein anwendungsspezifisches Benutzeroberflächeobjekt entspricht.  
  
 Beide Kategorien Meldungen nehmen keine Argumente und geben keinen Wert zurück.  
  
## Siehe auch  
 [Deklarieren von Meldungshandlerfunktionen](../mfc/declaring-message-handler-functions.md)