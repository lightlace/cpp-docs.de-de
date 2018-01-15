---
title: 'ActiveX-Steuerelementcontainer: Verwenden von Steuerelementen in einem Container Non-Dialog | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Create method [MFC], ActiveX controls
- CreateControl method [MFC]
- ActiveX controls [MFC], creating
- ActiveX control containers [MFC], non-dialog containers
- ActiveX control containers [MFC], inserting controls
ms.assetid: 46f195b0-b8ca-4409-8cca-fbfaf2c9ab9f
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c380d0a525c2f026054ebae1812450c4d4634c1e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="activex-control-containers-using-controls-in-a-non-dialog-container"></a>ActiveX-Steuerelementcontainer: Verwenden von Steuerelementen in Containern, die keine Dialogfelder sind
In einigen Anwendungen, z. B. eine SDI oder MDI-Anwendung sollten Sie ein Steuerelement in einem Fenster der Anwendung eingebettet. Die **erstellen** Memberfunktion die Wrapperklasse eingefügt, die von Visual C++ kann eine Instanz des Steuerelements dynamisch erstellen, ohne die Notwendigkeit für ein Dialogfeld.  
  
 Die **erstellen** Memberfunktion weist die folgenden Parameter:  
  
 `lpszWindowName`  
 Ein Zeiger auf den Text in die Eigenschaft des Steuerelements oder Beschriftungstitel (sofern vorhanden) angezeigt werden.  
  
 `dwStyle`  
 Windows-Formate. Eine vollständige Liste finden Sie unter [CWnd:: CreateControl](../mfc/reference/cwnd-class.md#createcontrol).  
  
 `rect`  
 Gibt die Größe und Position des Steuerelements.  
  
 `pParentWnd`  
 Gibt an, das Steuerelement übergeordnetes Fenster, in der Regel eine `CDialog`. Es muss nicht **NULL**.  
  
 `nID`  
 Gibt an, die Steuerelement-ID und können vom Container verwendet werden, um auf das Steuerelement zu verweisen.  
  
 Ein Beispiel für diese Funktion verwenden, um ein ActiveX-Steuerelement dynamisch zu erstellen, wäre in eine Formularansicht einer SDI-Anwendung. Sie können dann erstellen Sie eine Instanz des Steuerelements in der `WM_CREATE` Handler der Anwendung.  
  
 In diesem Beispiel `CMyView` ist die Klasse Hauptansicht `CCirc` ist die Wrapperklasse und CIRC. H ist der Header (. H)-Datei von der Wrapperklasse.  
  
 Diese Funktion ist eine vier Schritten bestehender Prozess.  
  
### <a name="to-dynamically-create-an-activex-control-in-a-non-dialog-window"></a>Um ein ActiveX-Steuerelement in einem Dialogfeld dynamisch zu erstellen  
  
1.  Fügen Sie CIRC. H in CMYVIEW. H, kurz vor dem Ausführen der `CMyView` Klassendefinition:  
  
     [!code-cpp[NVC_MFC_AxCont#12](../mfc/codesnippet/cpp/activex-control-containers-using-controls-in-a-non-dialog-container_1.h)]  
  
2.  Hinzufügen eine Membervariablen gespeichert (des Typs `CCirc`) zum geschützten Abschnitt von der `CMyView` befindet sich im CMYVIEW Klassendefinition. H  
  
     [!code-cpp[NVC_MFC_AxCont#13](../mfc/codesnippet/cpp/activex-control-containers-using-controls-in-a-non-dialog-container_2.h)]  
    [!code-cpp[NVC_MFC_AxCont#14](../mfc/codesnippet/cpp/activex-control-containers-using-controls-in-a-non-dialog-container_3.h)]  
  
3.  Hinzufügen einer `WM_CREATE` Nachrichtenhandler Klasse `CMyView`.  
  
4.  In der Handlerfunktion `CMyView::OnCreate`, einen Aufruf an des Steuerelements `Create` -Funktion mit dem **dies** Zeiger als das übergeordnete Fenster:  
  
     [!code-cpp[NVC_MFC_AxCont#15](../mfc/codesnippet/cpp/activex-control-containers-using-controls-in-a-non-dialog-container_4.cpp)]  
  
5.  Erstellen Sie das Projekt neu. Ein Steuerelement Circ wird dynamisch erstellt werden, wenn die Anwendung Ansicht erstellt wird.  
  
## <a name="see-also"></a>Siehe auch  
 [ActiveX-Steuerelementcontainer](../mfc/activex-control-containers.md)

