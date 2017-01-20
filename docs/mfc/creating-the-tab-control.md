---
title: "Erstellen des Registersteuerelements"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "TCS_EX_REGISTERDROP"
  - "TCS_EX_FLATSEPARATORS"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTabCtrl-Klasse, Erstellen"
  - "Registerkarten-Steuerelemente, Erstellen"
  - "TCS_EX_FLATSEPARATORS (erweiterter Stil)"
  - "TCS_EX_REGISTERDROP (erweiterter Stil)"
ms.assetid: 3a9c2d64-f5f4-41ea-84ab-fceb73c3dbdc
caps.latest.revision: 11
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Erstellen des Registersteuerelements
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wie das Registersteuerelement erstellt wird, hängt davon ab, ob Sie das Steuerelement in einem Dialogfeld verwenden oder in einem nondialog Fenster erstellen.  
  
### So CTabCtrl direkt in einem Dialogfeld verwendet werden  
  
1.  Im Dialog\-Editor fügen Sie einem Registersteuerelement der Dialogfeldvorlagen\-Ressource hinzu.  Geben Sie an seiner Steuerelement\-ID  
  
2.  Verwenden Sie [Assistent zum Hinzufügen von Membervariablen](../ide/adding-a-member-variable-visual-cpp.md), um eine Membervariable vom Typ [CTabCtrl](../mfc/reference/ctabctrl-class.md) mit der Steuerelementeigenschaft hinzuzufügen.  Sie können diesen Member verwenden, um `CTabCtrl`\-Memberfunktionen aufrufen.  
  
3.  Zuordnungshandlerfunktionen in Dialogklasse für alle Tab\-Steuerelement\-Benachrichtigungsmeldungen, die Sie bearbeiten müssen.  Weitere Informationen finden Sie unter [Zuordnung von Meldungen zu Funktionen](../mfc/reference/mapping-messages-to-functions.md).  
  
4.  In [OnInitDialog](../Topic/CDialog::OnInitDialog.md) legen Sie die Stile für `CTabCtrl` fest.  
  
### So CTabCtrl in einem nondialog Fenster verwenden  
  
1.  Definieren Sie das Steuerelement in der Ansicht oder der Fensterklasse.  
  
2.  Rufen Sie die Memberfunktion [Erstellen](../Topic/CTabCtrl::Create.md) des Steuerelements, möglicherweise in [OnInitialUpdate](../Topic/CView::OnInitialUpdate.md), möglicherweise schon in der [OnCreate](../Topic/CWnd::OnCreate.md)\-Handlerfunktion des übergeordneten Fensters auf \(wenn Sie das Steuerelement unterordnen\).  Legen Sie die Stile für das Steuerelement fest.  
  
 Nachdem das `CTabCtrl`\-Objekt erstellt wurde, können Sie die folgenden erweiterten Stile festlegen oder deaktivieren:  
  
-   **TCS\_EX\_FLATSEPARATORS** das Registersteuerelement zeichnet Trennzeichen zwischen den Registerkartenelementen.  Dieses weiterführende Format beeinflusst nur Tab\-Steuerelemente, die die **TCS\_BUTTONS** und **TCS\_FLATBUTTONS** Formate aufweisen.  Standardmäßig legt das Erstellen des Registersteuerelements mit dem **TCS\_FLATBUTTONS** Format erweiterte Stil fest.  
  
-   **TCS\_EX\_REGISTERDROP** das Registersteuerelement generiert **TCN\_GETOBJECT** Benachrichtigungsmeldungen, um ein Ablagezielobjekt bitten, wenn ein Objekt über die Registerelemente im Steuerelement gezogen wird.  
  
    > [!NOTE]
    >  Um die **TCN\_GETOBJECT** Benachrichtigung zu erhalten, müssen Sie die OLE\-Bibliotheken mit einem Aufruf von [AfxOleInit](../Topic/AfxOleInit.md) initialisieren.  
  
 Diese Formate können, nachdem das Steuerelement erstellt wurde, mit jeweiligen Aufrufen abgerufen und festgelegt werden auf die [GetExtendedStyle](../Topic/CTabCtrl::GetExtendedStyle.md) und [SetExtendedStyle](../Topic/CTabCtrl::SetExtendedStyle.md)\-Memberfunktionen.  
  
 Legen Sie beispielsweise das **TCS\_EX\_FLATSEPARATORS** Stil mit den folgenden Codezeilen fest:  
  
 [!CODE [NVC_MFCControlLadenDialog#33](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCControlLadenDialog#33)]  
  
 Deaktivieren Sie das **TCS\_EX\_FLATSEPARATORS** Stil von einem `CTabCtrl`\-Objekt mit den folgenden Codezeilen:  
  
 [!CODE [NVC_MFCControlLadenDialog#34](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCControlLadenDialog#34)]  
  
 Dies entfernt die Trennzeichen, die zwischen den Schaltflächen des `CTabCtrl`\-Objekts angezeigt werden.  
  
## Siehe auch  
 [Verwenden von CTabCtrl](../mfc/using-ctabctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)