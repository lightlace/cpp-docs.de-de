---
title: "Typsicherer Zugriff auf die Steuerelemente in einem Dialogfeld"
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
  - "Allgemeine Steuerelemente [C++], in Dialogfeldern"
  - "Steuerelemente [MFC], Zugriff in Dialogfeldern"
  - "Dialogfelder [C++], Typsicherer Zugriff auf Steuerelemente"
  - "MFC-Dialogfelder, Typsicherer Zugriff auf Steuerelemente"
  - "Sicherer Zugriff auf Dialogfeld-Steuerelemente"
  - "Typsicherer Zugriff auf Dialogfeld-Steuerelemente"
  - "Allgemeine Windows-Steuerelemente [C++], in Dialogfeldern"
ms.assetid: 67021025-dd93-4d6a-8bed-a1348fe50685
caps.latest.revision: 9
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Typsicherer Zugriff auf die Steuerelemente in einem Dialogfeld
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die Steuerelemente in einem Dialogfeld können die Schnittstellen von MFC\-Steuerelementklassen wie `CListBox` und `CEdit` nutzen.  Sie können ein Steuerelementobjekt erstellen und es an ein Dialogsteuerelement anhängen.  Dann können Sie auf das Steuerelement über seine Klassenschnittstelle zugreifen und Memberfunktionen aufrufen, die für das Steuerelement ausgeführt werden sollen.  Die hier beschriebenen Methoden bieten einen typsicheren Zugriff auf ein Steuerelement.  Dies ist speziell für Steuerelemente wie Bearbeitungsfelder und Listenfelder nützlich.  
  
 Es gibt zwei Methoden, um eine Verbindung zwischen einem Steuerelement in einem Dialogfeld und einer C\+\+\-Steuerelement\-Membervariable in einer von `CDialog` abgeleiteten Klasse herzustellen:  
  
-   [Ohne Code\-Assistenten](../mfc/type-safe-access-to-controls-without-code-wizards.md)  
  
-   [Mit Code\-Assistenten](../mfc/type-safe-access-to-controls-with-code-wizards.md)  
  
## Siehe auch  
 [Dialogfelder](../mfc/dialog-boxes.md)