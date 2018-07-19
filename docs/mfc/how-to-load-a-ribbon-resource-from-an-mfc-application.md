---
title: 'Vorgehensweise: Laden einer Menübandressource aus einer Mfc_anwendung | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ribbon resource [MFC], loading
ms.assetid: 1c76bb8f-6345-414a-9f3f-128815ceadc5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b014e1725ae6c5043c051242a74e29338c3ef2d6
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
ms.locfileid: "33344190"
---
# <a name="how-to-load-a-ribbon-resource-from-an-mfc-application"></a>Gewusst wie: Laden einer Menübandressource aus einer MFC-Anwendung
Um die menübandressource in Ihrer Anwendung verwenden möchten, ändern Sie die Anwendung zum Laden der menübandressource.  
  
### <a name="to-load-a-ribbon-resource"></a>Beim Laden einer menübandressource  
  
1.  Deklarieren Sie die `Ribbon Control` Objekt in der `CMainFrame` Klasse.  
  
 ```  
    CMFCRibbonBar m_wndRibbonBar;   
 ```  
  
2.  In `CMainFrame::OnCreate`, erstellen und initialisieren Sie das Steuerelement im Menüband.  
  
 ```  
    if (!m_wndRibbonBar.Create (this))  
 {  
    return -1;  
 }  
 
    if (!m_wndRibbonBar.LoadFromResource(IDR_RIBBON))  
 {  
    return -1;  
 }  
 ```  
  
## <a name="see-also"></a>Siehe auch  
 [Menüband-Designer (MFC)](../mfc/ribbon-designer-mfc.md)

