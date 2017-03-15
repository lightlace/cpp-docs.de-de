---
title: "Festlegen der Bilder f&#252;r ein bestimmtes Element | Microsoft Docs"
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
  - "Erweiterte Kombinationsfelder, Bilder"
  - "Bilder [C++], Kombinationsfeldelemente"
ms.assetid: bde83db8-23a7-4e35-837a-c86447d2c0af
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Festlegen der Bilder f&#252;r ein bestimmtes Element
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Die verschiedenen Bildern, die das erweiterte ComboBox\-Steuerelement verwendet werden, werden durch die Werte in `iImage`, **iSelectedImage** und **iOverlay**\-Member der [COMBOBOXEXITEM](http://msdn.microsoft.com/library/windows/desktop/bb775746)\-Struktur bestimmt.  Jeder Wert ist der Index eines Bildes in der zugeordneten Bildliste des Steuerelements.  Standardmäßig sind diese Member auf 0 festgelegt und im Steuerelement, kein Bild für das Element anzuzeigen.  Wenn Sie Bilder für ein bestimmtes Element verwenden möchten, können Sie die Struktur, eine entsprechend ändern, wenn Sie das ComboBox\-Steuerelement einfügen oder, indem Sie ein vorhandenes ComboBox\-Steuerelement ändern.  
  
## Festlegen des Bilds für ein neues Element  
 Wenn Sie ein neues Element einfügen, initialisieren Sie `iImage`, **iSelectedImage** und **iOverlay**\-Strukturmember mit den richtigen Werten und fügen Sie dann das Element mit einem Aufruf von [CComboBoxEx::InsertItem](../Topic/CComboBoxEx::InsertItem.md).  
  
 Im folgenden Beispiel wird ein neues erweitertes ComboBox\-Steuerelement \(`cbi`\) in dem erweiterte Kombinationsfeld\-Steuerelement \(`m_comboEx`\) und gibt Indizes für alle drei Bildzustände an:  
  
 [!CODE [NVC_MFCControlLadenDialog#12](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCControlLadenDialog#12)]  
  
## Festlegen des Bilds für ein vorhandenes Element  
 Wenn Sie ein vorhandenes Element ändern, müssen Sie mit dem **mask**\-Member einer **COMBOBOXEXITEM**\-Struktur arbeiten.  
  
#### Um ein vorhandenes Element ändern, um Bilder zu verwenden  
  
1.  Deklarieren Sie eine **COMBOBOXEXITEM**\-Struktur und den **mask** \- Datenmember auf die Werte fest, die Sie sich interessieren, zu ändern.  
  
2.  Verwenden dieser Struktur machen Sie [CComboBoxEx::GetItem](../Topic/CComboBoxEx::GetItem.md) einen Aufruf.  
  
3.  Ändern Sie **mask**, **iSelectedImage**`iImage` und Member der neu zurückgegebenen Struktur, mit der entsprechenden Werte.  
  
4.  Führen Sie [CComboBoxEx::SetItem](../Topic/CComboBoxEx::SetItem.md) einen Aufruf und die geänderte Struktur übergeben.  
  
 Im folgenden Beispiel wird dieses Verfahren veranschaulicht, indem die ausgewählten und nicht ausgewählten Bilder des dritten erweiterten Kombinationsfelds austauscht:  
  
 [!CODE [NVC_MFCControlLadenDialog#13](../CodeSnippet/VS_Snippets_Cpp/NVC_MFCControlLadenDialog#13)]  
  
## Siehe auch  
 [Verwenden von CComboBoxEx](../mfc/using-ccomboboxex.md)   
 [Steuerelemente](../mfc/controls-mfc.md)