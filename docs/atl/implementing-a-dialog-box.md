---
title: Implementieren eines Dialogfelds | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CSimpleDialog class, implementing dialog boxes in ATL
- dialog boxes, ATL
- CAxDialogImpl class, implementing dialog boxes in ATL
- ATL, dialog boxes
ms.assetid: 478525f2-aa6a-435a-b162-68fc8aa98a8e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 672696027a43cd5a50e2ad630824d305f7ca4b68
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
ms.locfileid: "32355851"
---
# <a name="implementing-a-dialog-box"></a>Implementieren eines Dialogfelds
Es gibt zwei Möglichkeiten, um ein Dialogfeld dem ATL-Projekt hinzuzufügen: mithilfe des ATL-Dialogfeld-Assistenten oder manuell hinzufügen.  
  
## <a name="adding-a-dialog-box-with-the-atl-dialog-wizard"></a>Hinzufügen eines Dialogfelds mit der ATL-Dialogfeld-Assistent  
 In der [Klasse hinzufügen (Dialogfeld)](../ide/add-class-dialog-box.md), wählen Sie das Objekt ATL-Dialogfeld, um ein Dialogfeld zum ATL-Projekt hinzufügen. Füllen Sie die ATL-Dialogfeld-Assistent nach Bedarf, und klicken Sie auf **Fertig stellen**. Fügt eine Klasse abgeleitet wurde. der Assistent [CAxDialogImpl](../atl/reference/caxdialogimpl-class.md) zu Ihrem Projekt. Öffnen Sie die Ressourcenansicht aus der **Ansicht** , suchen Sie das Dialogfeld, und doppelklicken Sie darauf, um sie in den Ressourcen-Editor zu öffnen.  
  
> [!NOTE]
>  Wenn das Dialogfeld von abgeleitet ist `CAxDialogImpl`, kann es sowohl ActiveX-hosten und Windows-Steuerelemente. Wenn Sie in Ihre Dialogfeldklasse nicht den Mehraufwand für ActiveX-Steuerelemente unterstützen möchten, verwenden Sie [CSimpleDialog](../atl/reference/csimpledialog-class.md) oder [CDialogImpl](../atl/reference/cdialogimpl-class.md) stattdessen.  
  
 Nachricht und Ereignishandler können Ihre Dialogfeldklasse von Klassenansicht hinzugefügt werden. Weitere Informationen finden Sie unter [hinzufügen eine ATL-Meldungshandlers](../atl/adding-an-atl-message-handler.md).  
  
## <a name="adding-a-dialog-box-manually"></a>Manuelles Hinzufügen von einem Dialogfeld  
 Implementieren eines Dialogfelds ähnelt der ein Fensters zu implementieren. Leiten Sie eine Klasse entweder [CAxDialogImpl](../atl/reference/caxdialogimpl-class.md), [CDialogImpl](../atl/reference/cdialogimpl-class.md), oder [CSimpleDialog](../atl/reference/csimpledialog-class.md) , und deklarieren Sie eine [meldungszuordnung](../atl/message-maps-atl.md) Nachrichten zu verarbeiten. Allerdings müssen Sie eine Dialogfeld Vorlage Ressourcen-ID in die abgeleitete Klasse angeben. Die Klasse benötigen einen Datenmember namens `IDD` , diesen Wert enthalten soll.  
  
> [!NOTE]
>  Wenn Sie ein Dialogfeld mit dem ATL-Dialogfeld-Assistenten erstellen, fügt der Assistent automatisch die `IDD` Element als ein `enum` Typ.  
  
 `CDialogImpl` bietet die Möglichkeit zum Implementieren eines modalen oder ein nicht modales Dialogfeld an, das Windows-Steuerelemente hostet. `CAxDialogImpl` bietet die Möglichkeit zum Implementieren eines modalen oder ein nicht modales Dialogfeld an, das ActiveX- und Windows-Steuerelemente hostet.  
  
 Um ein modales Dialogfeld erstellen möchten, erstellen Sie eine Instanz von Ihr `CDialogImpl`-abgeleitet (oder `CAxDialogImpl`-abgeleitet) Klasse, und rufen Sie anschließend die [DoModal](../atl/reference/cdialogimpl-class.md#domodal) Methode. Um ein modales Dialogfeld zu schließen, rufen Sie die ["EndDialog"](../atl/reference/cdialogimpl-class.md#enddialog) Methode von einem Message-Handler. Um ein nicht modales Dialogfeld erstellen möchten, rufen die [erstellen](../atl/reference/cdialogimpl-class.md#create) Methode anstelle von `DoModal`. Aufrufen, um ein nicht modales Dialogfeld zu zerstören, [DestroyWindow](../atl/reference/cdialogimpl-class.md#destroywindow).  
  
 Auffangen von Ereignissen erfolgt automatisch [CAxDialogImpl](../atl/reference/caxdialogimpl-class.md). Implementieren Sie Meldungshandler des Dialogfelds, wie die Ereignishandler in einem `CWindowImpl`-abgeleitete Klasse. Ist ein Rückgabewert Message-spezifische, zurückzugeben als ein `LRESULT`. Das zurückgegebene `LRESULT` Werte von ATL für die ordnungsgemäße Behandlung durch den Windows-Dialogfeld-Manager zugeordnet sind. Einzelheiten finden Sie in den Quellcode für [CDialogImplBaseT:: DialogProc](../atl/reference/cdialogimpl-class.md#dialogproc) in atlwin.h aufgetreten.  
  
## <a name="example"></a>Beispiel  
 Die folgende Klasse implementiert einen (Dialogfeld):  
  
 [!code-cpp[NVC_ATL_Windowing#66](../atl/codesnippet/cpp/implementing-a-dialog-box_1.h)]  
  
## <a name="see-also"></a>Siehe auch  
 [Fensterklassen](../atl/atl-window-classes.md)

