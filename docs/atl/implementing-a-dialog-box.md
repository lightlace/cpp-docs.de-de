---
title: "Implementing a Dialog Box"
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
  - "ATL, Dialogfelder"
  - "CAxDialogImpl class, implementing dialog boxes in ATL"
  - "CSimpleDialog class, implementing dialog boxes in ATL"
  - "Dialogfelder, ATL"
ms.assetid: 478525f2-aa6a-435a-b162-68fc8aa98a8e
caps.latest.revision: 10
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Implementing a Dialog Box
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Es gibt zwei Möglichkeiten, ein Dialogfeld dem ATL\-Projekt hinzuzufügen: verwenden Sie den ATL\-Dialogfeld\-Assistenten oder fügen Sie ihn manuell hinzu.  
  
## Hinzufügen eines Dialogfelds mit dem ATL\-Dialogfeld\-Assistenten  
 In [Fügen Sie Klassendialogfeld hinzu](../ide/add-class-dialog-box.md) wählen Sie das ATL\-Dialogfeld\-Objekt aus, um ein Dialogfeld dem ATL\-Projekt hinzuzufügen.  Fügen Sie den ATL\-Dialogfeld\-Assistenten bzw. aus und klicken Sie auf **Fertig stellen**.  Der Assistent fügt eine Klasse hinzu, die von [CAxDialogImpl](../atl/reference/caxdialogimpl-class.md) dem Projekt abgeleitet wird.  Öffnen Sie die Ressourcenansicht aus dem Menü **Ansicht**, suchen Sie das Dialogfeld und doppelklicken Sie darauf, um es im Ressourcen\-Editor zu öffnen.  
  
> [!NOTE]
>  Wenn das Dialogfeld von `CAxDialogImpl` abgeleitet ist, kann es ActiveX\- und Windows\-Steuerelemente hosten.  Wenn Sie nicht den Aufwand der ActiveX\-Steuerelement\-Unterstützung in der Dialogfeldklasse soll, verwenden Sie [CSimpleDialog](../atl/reference/csimpledialog-class.md) oder [CDialogImpl](../atl/reference/cdialogimpl-class.md) stattdessen.  
  
 Meldung und Ereignishandler können in der Dialogfeldklasse in der Klassenansicht hinzugefügt werden.  Weitere Informationen finden Sie unter [Hinzufügen eines ATL\-Meldungshandlers](../atl/adding-an-atl-message-handler.md).  
  
## Ein Dialogfeld manuell hinzufügen  
 Ein Dialogfeld zu implementieren ist zum Implementieren eines Fensters ähnlich.  Sie leiten eine Klasse entweder von [CAxDialogImpl](../atl/reference/caxdialogimpl-class.md), von [CDialogImpl](../atl/reference/cdialogimpl-class.md) oder von [CSimpleDialog](../atl/reference/csimpledialog-class.md) und deklarieren [Meldungszuordnung](../atl/message-maps-atl.md) zu den Handlemeldungen.  Sie müssen jedoch Dialogfeldvorlagenressourcen\-ID in der abgeleiteten Klasse auch angeben.  Die Klasse muss einen Datenmember verfügen, der `IDD` aufgerufen wird, damit dieser Wert aufzunehmen.  
  
> [!NOTE]
>  Wenn Sie ein Dialogfeld mithilfe des ATL\-Dialogfeld\-Assistenten erstellen, fügt der Assistent automatisch den `IDD`\-Member als `enum`\-Typ hinzu.  
  
 `CDialogImpl` ermöglicht es Ihnen, ein modales oder ein nicht modales Dialogfeld implementieren, das Windows\-Steuerelemente hostet.  `CAxDialogImpl` ermöglicht es Ihnen, ein modales oder ein nicht modales Dialogfeld implementieren, das ActiveX\- und Windows\-Steuerelemente hostet.  
  
 Um ein modales Dialogfeld zu erstellen, erstellen Sie eine Instanz aus dem `CDialogImpl` von abgeleitete \(oder `CAxDialogImpl`\- Klasse abgeleitet\) und dann die [DoModal](../Topic/CDialogImpl::DoModal.md)\-Methode auf.  Um ein modales Dialogfeld zu schließen, rufen Sie die Methode von einem [EndDialog](../Topic/CDialogImpl::EndDialog.md) Meldungshandler auf.  Um ein nicht modales Dialogfeld zu erstellen, rufen Sie die Methode anstelle [Erstellen Sie](../Topic/CDialogImpl::Create.md)`DoModal` auf.  Um ein nicht modales Dialogfeld zu zerstören, rufen Sie [DestroyWindow](../Topic/CDialogImpl::DestroyWindow.md) auf.  
  
 Das Verringern von Ereignissen wird automatisch in [CAxDialogImpl](../atl/reference/caxdialogimpl-class.md) durchgeführt.  Implementieren Sie die Meldungshandler des Dialogfelds, wie Sie die Handler in `CWindowImpl` von abgeleitete Klasse wurden.  Wenn eine der meldungsspezifischen Rückgabewert gibt, geben Sie ihn als `LRESULT` zurück.  Die zurückgegebenen `LRESULT`\-Werte werden von ATL für eine ordnungsgemäße Behandlung durch den Windows\-Dialogfeldmanager zugeordnet.  Details finden Sie den Quellcode für [CDialogImplBaseT::DialogProc](../Topic/CDialogImpl::DialogProc.md) in atlwin.h.  
  
## Beispiel  
 Die folgende Klasse implementiert ein Dialogfeld:  
  
 [!CODE [NVC_ATL_Windowing#66](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Windowing#66)]  
  
## Siehe auch  
 [Fensterklassen](../atl/atl-window-classes.md)