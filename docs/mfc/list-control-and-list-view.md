---
title: Listensteuerelement und Listenansichtsteuerelement | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- CListView class [MFC], and CListCtrl
- views [MFC], list and list control
- CListCtrl class [MFC], and CListView
- list views [MFC]
- list controls [MFC], List view
ms.assetid: 7aee1c48-b158-4399-be0b-be366993665e
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 46c9d559d642b6edf926b9feb49332ef7ec2924a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="list-control-and-list-view"></a>Listensteuerelement und Listenansichtsteuerelement
Der Einfachheit halber kapselt MFC das Strukturelement-Steuerelement auf zwei Arten. Sie können den List-Steuerelemente verwenden:  
  
-   Direkt durch das Einbetten einer [CListCtrl](../mfc/reference/clistctrl-class.md) Objekt in einer Dialogfeldklasse.  
  
-   Indirekt mithilfe der Klasse [CListView](../mfc/reference/clistview-class.md).  
  
 `CListView`ganz einfach ein Listenfeld-Steuerelement in der MFC-Dokument-/Ansichtarchitektur, das Steuerelement kapseln integrieren ähnlich wie [CEditView](../mfc/reference/ceditview-class.md) kapselt ein Bearbeitungssteuerelement: das Steuerelement füllt die gesamte Oberfläche der MFC-Ansicht. (Die Sicht *ist* im Steuerelement umgewandelt `CListView`.)  
  
 Ein `CListView` Objekt erbt die [CCtrlView](../mfc/reference/cctrlview-class.md) und Basistext Klassen und fügt eine Memberfunktion, um das zugrunde liegende Listensteuerelement abzurufen. Verwenden Sie Mitglieder anzeigen möchten, um mit der Sicht als Sicht arbeiten. Verwenden der [GetListCtrl](../mfc/reference/clistview-class.md#getlistctrl) Memberfunktion für den Zugriff auf das Strukturelement-Steuerelement-Memberfunktionen. Verwenden Sie diese Member zu:  
  
-   Fügen Sie hinzu, löschen Sie oder bearbeiten Sie "Elemente" in der Liste.  
  
-   Festlegen Sie oder rufen Sie der Liste Steuerelementattribute ab.  
  
 Abrufen eines Verweises auf die `CListCtrl` zugrunde liegenden eine `CListView`, rufen Sie `GetListCtrl` aus Ihrer Listenansichtsklasse:  
  
 [!code-cpp[NVC_MFCListView#4](../atl/reference/codesnippet/cpp/list-control-and-list-view_1.cpp)]  
  
 Dieses Thema beschreibt die beiden Möglichkeiten, das Strukturelement-Steuerelement zu verwenden.  
  
## <a name="see-also"></a>Siehe auch  
 [Verwenden von CListCtrl](../mfc/using-clistctrl.md)   
 [Steuerelemente](../mfc/controls-mfc.md)

