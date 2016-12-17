---
title: "Adding an ATL Dialog Box"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL-Projekte, Hinzufügen von Dialogressourcen"
  - "Dialogfelder, ATL"
  - "MFC-Dialogfelder, ATL-Dialogfelder"
ms.assetid: 152a378f-7b24-4f66-aeba-c740973f03a6
caps.latest.revision: 10
caps.handback.revision: "5"
ms.author: "mblome"
manager: "ghogen"
---
# Adding an ATL Dialog Box
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ein ATL\-Dialogfeld kann einem Projekt nur hinzugefügt werden, wenn es sich entweder um ein ATL\-Projekt oder um ein MFC\-Projekt mit integrierter ATL\-Unterstützung handelt.  Sie können den [ATL\-Projekt\-Assistenten](../../atl/reference/atl-project-wizard.md) verwenden, um eine ATL\-Anwendung zu erstellen, oder der [MFC\-Anwendung ein ATL\-Objekt hinzufügen](../../mfc/reference/adding-atl-support-to-your-mfc-project.md), um die ATL\-Unterstützung in eine MFC\-Anwendung zu implementieren.  
  
 Der ATL\-Dialogfeld\-Assistent implementiert normalerweise ein von [CAxDialogImpl](../../atl/reference/caxdialogimpl-class.md) abgeleitetes Dialogfeld.  Diese Klasse enthält auch die Hostunterstützung für ActiveX\- und Windows\-Steuerelemente.  Wenn Sie auf den zusätzlichen Aufwand in Zusammenhang mit der Unterstützung von ActiveX\-Steuerelementen verzichten möchten, ersetzen Sie, nachdem der Code vom Assistenten generiert wurde, alle Instanzen von `CAxDialogImpl` durch [CSimpleDialog](../../atl/reference/csimpledialog-class.md) oder [CDialogImpl](../../atl/reference/cdialogimpl-class.md) als Basisklasse.  
  
> [!NOTE]
>  `CSimpleDialog` erstellt nur modale Dialogfelder, die nur allgemeine Windows\-Steuerelemente unterstützen.  `CDialogImpl` erstellt entweder modale Dialogfelder oder Dialogfelder ohne Modus.  
  
### So fügen Sie dem Projekt eine ATL\-Dialogressource hinzu  
  
1.  Erstellen Sie ein ATL\-Projekt mithilfe des [ATL\-Projekt\-Assistenten](../../atl/reference/atl-project-wizard.md).  
  
2.  Klicken Sie in der [Klassenansicht](assetId:///8d7430a9-3e33-454c-a9e1-a85e3d2db925) mit der rechten Maustaste auf den Projektnamen, und klicken Sie dann im Kontextmenü auf **Hinzufügen**.  Klicken Sie auf **Klasse hinzufügen**.  
  
3.  Klicken Sie im Bereich **Vorlagen** des Dialogfelds [Klasse hinzufügen](../../ide/add-class-dialog-box.md) auf **ATL\-Dialogfeld**.  Klicken Sie auf **Öffnen**, um den [ATL\-Dialogfeld\-Assistenten](../../atl/reference/atl-dialog-wizard.md) zu öffnen.  
  
 Weitere Informationen finden Sie unter [Implementieren eines Dialogfelds](../../atl/implementing-a-dialog-box.md).  
  
## Siehe auch  
 [Hinzufügen einer Klasse](../../ide/adding-a-class-visual-cpp.md)   
 [Fensterklassen](../../atl/atl-window-classes.md)   
 [Message Maps](../../atl/message-maps-atl.md)