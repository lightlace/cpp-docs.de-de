---
title: "Typsicherer Zugriff auf Steuerelemente mit Code-Assistenten"
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
  - "Code-Assistenten"
  - "DDX (Dialog Data Exchange – Dialogdatenaustausch), Zugriff auf Steuerelemente"
  - "Dialogfeldsteuerelemente, Aufrufen"
  - "Dialogfelder, Zugriff auf Steuerelemente"
ms.assetid: b8874393-ee48-4124-8d78-e3648a7e29b9
caps.latest.revision: 11
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# Typsicherer Zugriff auf Steuerelemente mit Code-Assistenten
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Wenn Sie mit DDX\-Funktionen vertraut sind, können Sie die Steuerelementeigenschaft in [Assistent zum Hinzufügen von Membervariablen](../ide/add-member-variable-wizard.md) verwenden, um Zugriff typsicheren zu erstellen.  Dieser Ansatz ist einfacher, als Steuerelemente ohne Code\-Assistenten erstellen.  
  
 Wenn Sie lediglich Zugriff auf den Wert eines Steuerelements soll, bereitstellt DDX ihn.  Wenn Sie mehr als möchten zugreifen auf den Wert eines Steuerelements, verwenden Sie den Assistenten zum Hinzufügen von Membervariablen, um eine Membervariable der entsprechenden Klasse der Dialogfeldklasse hinzuzufügen.  Fügen Sie diese der Membervariable Steuerelementeigenschaft an.  
  
 Membervariablen können eine Steuerelementeigenschaft anstelle einer Value\-Eigenschaft haben.  Die Value\-Eigenschaft verweist auf den Typ von Daten, die vom Steuerelement, wie `CString` oder `int` zurückgegeben werden.  Die Steuerelementeigenschaft aktiviert Zugriff auf das Steuerelement durch einen Datenmember, dessen Typ eine der Steuerelementklassen in MFC, wie `CButton` oder `CEdit` ist.  
  
> [!NOTE]
>  Für ein angegebenes Steuerelement können Sie, wenn Sie möchten, weisen mehrere Membervariablen mit der Value\-Eigenschaft und höchstens einköpfige Variable mit der Steuerelementeigenschaft.  Sie können nur ein MFC\-Objekt verfügen, das auf einem Steuerelement zugeordnet wird, da die mehrere Objekte, die an ein Steuerelement angefügt wurden, oder ein anderes Fenster, zu Mehrdeutigkeiten in der Meldungszuordnung führen würden.  
  
 Sie können dieses Objekt verwenden, um alle Memberfunktionen zum Steuerelementobjekt aufzurufen.  Diese Aufrufe wirken sich auf das Steuerelement im Dialogfeld.  Beispielsweise für einen Checkbox\-Steuerelement, das durch die Variable `m_Checkbox`, des Typs `CButton` dargestellt wurde, konnten Sie aufrufen:  
  
 [!CODE [NVC_MFCControlLadenDialog#52](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCControlLadenDialog#52)]  
  
 Hier dient die `m_Checkbox`\-Membervariable den gleichen Zweck wie die Memberfunktionen `GetMyCheckbox`, das in [Typsicherer Zugriff an Steuerelemente ohne Code\-Assistenten](../mfc/type-safe-access-to-controls-without-code-wizards.md) gezeigt wird.  Wenn das Kontrollkästchen keine automatische Kontrollkästchen ist, können Sie dennoch einen Handler in der Dialogfeldklasse für die **BN\_CLICKED**\-Steuerelement\-Benachrichtigung erfordern, wenn auf die Schaltfläche geklickt wird.  
  
 Weitere Informationen zu Steuerelementen, finden Sie unter [Steuerelemente](../mfc/controls-mfc.md).  
  
## Siehe auch  
 [Typsicherer Zugriff auf die Steuerelemente in einem Dialogfeld](../mfc/type-safe-access-to-controls-in-a-dialog-box.md)   
 [Lebenszyklus eines Dialogfelds](../mfc/life-cycle-of-a-dialog-box.md)   
 [Typsicherer Zugriff auf Steuerelemente ohne Code\-Assistenten](../mfc/type-safe-access-to-controls-without-code-wizards.md)