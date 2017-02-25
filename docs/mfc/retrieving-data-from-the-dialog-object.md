---
title: "Abrufen von Daten aus dem Dialogfeldobjekt | Microsoft Docs"
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
  - "Erfassen der Benutzereingabe"
  - "Daten [MFC], Dialogfelder"
  - "Daten [MFC], Abrufen"
  - "Datenabruf [C++], Dialogfelder"
  - "DDX (Dialog Data Exchange – Dialogdatenaustausch) [C++]"
  - "DDX (Dialog Data Exchange – Dialogdatenaustausch) [C++], Informationen über DDX"
  - "DDX (Dialog Data Exchange – Dialogdatenaustausch) [C++], Abrufen von Daten aus dem Dialogfeldobjekt"
  - "Dialogfeldsteuerelemente [C++], Initialisieren von Werten"
  - "Dialogfelddaten [C++]"
  - "Dialogfelddaten [C++], Abrufen"
  - "Dialogfelder [C++], Abrufen von Benutzerdaten"
  - "GetDlgItemText-Methode"
  - "GetWindowText-Methode"
  - "MFC-Dialogfelder, Abrufen der Benutzereingabe"
  - "Abrufen von Daten"
  - "SetDlgItemText-Methode"
  - "SetWindowText-Methode"
  - "Benutzereingabe [C++], Abrufen aus MFC-Dialogfeldern"
ms.assetid: bdca2b61-6b53-4c2e-b426-8712c7a38ec0
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Abrufen von Daten aus dem Dialogfeldobjekt
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Das Framework stellt eine einfache Möglichkeit, um die Werte von Steuerelementen in einem Dialogfeld zu initialisieren und Werte von Steuerelementen abrufen.  Der mühsamere manuelle Ansatz ist, Funktionen wie `SetDlgItemText` und `GetDlgItemText`\-Memberfunktionen der Klasse `CWnd` aufzurufen, die auf Steuerfenster gelten.  Mit diesen Features greifen Sie auf jedes Steuerelement einzeln zu, um den Wert, aufrufenden Funktionen wie `SetWindowText` und `GetWindowText` festzulegen bzw. abzurufen.  Der Ansatz des Frameworks automatisiert Initialisierung und Abrufen.  
  
 Dialogdatenaustausch \(DDX\) können Sie Daten zwischen den Steuerelementen im Dialogfeld und Membervariablen im Dialogfeldobjekt leicht.  Dieser Austausch bearbeitet beide Methoden.  Um die Steuerelemente im Dialogfeld zu initialisieren, können Sie die Werte von Datenmembern im Dialogfeldobjekt festlegen, und das Framework überträgt die Werte an Steuerelemente bevor das Dialogfeld angezeigt wird.  Anschließend können Sie die Dialogfelddatenmember mit Daten jederzeit aktualisieren, die vom Benutzer eingegeben werden.  An diesem Punkt können Sie die Daten verwenden, indem Sie die Datenmembervariablen verweisen.  
  
 Sie können für die Werte mit Dialogfelddatenvalidierung \(DDV\) von automatisch überprüft werden Dialogfeldkontrollen auch anordnen.  
  
 DDX und DDV werden in [Dialogdatenaustausch und Validierung](../mfc/dialog-data-exchange-and-validation.md) erläutert.  
  
 Ein modales Dialogfeld können Sie alle Daten abrufen der eingegebene Benutzer, wenn `DoModal`**IDOK** zurückgibt, aber bevor das Dialogfeldobjekt zerstört wird.  Ein nicht modales Dialogfeld können Sie Daten im Dialogfeldobjekt jederzeit abrufen, indem Sie `UpdateData` mit dem Argument **TRUE** aufrufen und dann auf Dialogfeldklassenmembervariablen zugreifen.  Dieser Begriff wird in [Dialogdatenaustausch und Validierung](../mfc/dialog-data-exchange-and-validation.md) erläutert.  
  
## Siehe auch  
 [Lebenszyklus eines Dialogfelds](../mfc/life-cycle-of-a-dialog-box.md)