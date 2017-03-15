---
title: "Hinzuf&#252;gen von Spalten zum Steuerelement (Berichtsansicht) | Microsoft Docs"
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
  - "CListCtrl-Klasse, Hinzufügen von Spalten"
  - "CListCtrl-Klasse, Berichtsanzeige"
  - "Spalten [C++], Hinzufügen zu CListCtrl"
  - "Berichtansicht in CListCtrl-Klasse"
  - "Ansichten, Bericht"
ms.assetid: 7392c0d7-f8a5-4e7b-9ae7-b53dc9dd80ae
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Hinzuf&#252;gen von Spalten zum Steuerelement (Berichtsansicht)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  Die folgenden Schritte veranschaulichen entweder auf [CListView](../mfc/reference/clistview-class.md) oder [Verwendung](../mfc/reference/clistctrl-class.md)\-Objekt zu.  
  
 Wenn ein Listensteuerelement in der Berichtsansicht ist, werden die Spalten angezeigt und bieten eine Möglichkeit zum Organisieren der verschiedenen Unterelemente jedes Listensteuerelementelements bereit.  Diese Organisation ist einer 1:1\-Entsprechung zwischen einer Spalte im Listensteuerelement und dem zugeordneten Unterelement des Listensteuerelementelements implementiert.  Weitere Informationen über Unterelemente, finden Sie unter [Hinzufügen von Elementen zum Steuerelement](../mfc/adding-items-to-the-control.md).  Ein Beispiel eines Listensteuerelements in der Berichtsansicht wird aus der Detailansicht in Windows 95 und Windows 98\-Explorer bereitgestellt.  Die erste Spalte wird Ordner, Dateisymbole und Bezeichnungen auf.  Andere Spaltenlistendateigröße, Dateityp, Datumslast Arbeiten, z. B.  
  
 Obwohl Spalten zu einem Listensteuerelement jederzeit hinzugefügt werden können, sind die Spalten angezeigt, wenn das Steuerelement das `LVS_REPORT` Stilbit verfügt, das aktiviert ist.  
  
 Jede Spalte verfügt über ein zugeordnetes Objekt des Kopfzeilenelements \(siehe [CHeaderCtrl](../mfc/reference/cheaderctrl-class.md)\), das die Spalte bezeichnet und Benutzern ermöglicht, um die Größe der Spalte zu ändern.  
  
 Wenn das Listensteuerelement eine Berichtsansicht unterstützt, müssen Sie eine Spalte für alle in einem Listensteuerelementelement Unterelement hinzufügen.  Fügen Sie eine Spalte hinzu, indem Sie eine [LV\_COLUMN](http://msdn.microsoft.com/library/windows/desktop/bb774743)\-Struktur vorbereiten und dann einen Aufruf [InsertColumn](../Topic/CListCtrl::InsertColumn.md) ausführen.  Nachdem Sie die erforderlichen Spalten \(die auch als Kopfzeilenelemente hinzugefügt haben, können Sie sie mithilfe der Memberfunktionen und Stile neu anordnen, die dem eingebetteten Header\-Steuerelement gehören.  Weitere Informationen finden Sie unter [Reihenfolgen\-Elemente im Header\-Steuerelement](../mfc/ordering-items-in-the-header-control.md).  
  
> [!NOTE]
>  Wenn das Listensteuerelement mit dem **LVS\_NOCOLUMNHEADER**  Stil erstellt wird, wird jeder Versuch, Spalten einzufügende ignoriert.  
  
## Siehe auch  
 [Verwenden von CListCtrl](../mfc/using-clistctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)