---
title: "Eine ATL-Dialogfeld hinzufügen | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs: C++
helpviewer_keywords:
- ATL projects, adding dialog resources
- MFC dialog boxes, ATL dialogs
- dialog boxes, ATL
ms.assetid: 152a378f-7b24-4f66-aeba-c740973f03a6
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d8c9969f4747c6c3fa2a39b7b0452f6ac54c9d58
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="adding-an-atl-dialog-box"></a>Eine ATL-Dialogfeld hinzufügen
Um dem Projekt eine ATL-Dialogfeld hinzufügen, muss das Projekt eine ATL-Projekt oder ein MFC-Projekt, das ATL-Unterstützung umfasst. Können Sie die [ATL-Projektassistenten](../../atl/reference/atl-project-wizard.md) zum Erstellen einer Anwendung ATL oder [Hinzufügen eines ATL-Objekts zu der MFC-Anwendung](../../mfc/reference/adding-atl-support-to-your-mfc-project.md) ATL-Unterstützung für eine MFC-Anwendung zu implementieren.  
  
 Standardmäßig implementiert die ATL-Dialogfeld-Assistent ein Dialogfeld abgeleitet [CAxDialogImpl](../../atl/reference/caxdialogimpl-class.md). Diese Klasse enthält Unterstützung für das hosting von ActiveX- und Windows-Steuerelemente. Wenn Sie nicht möchten den Aufwand für das ActiveX-Steuerelemente unterstützen, nachdem der Assistent Code generiert wurde, ersetzen Sie alle Instanzen von `CAxDialogImpl` entweder mit [CSimpleDialog](../../atl/reference/csimpledialog-class.md) oder [CDialogImpl](../../atl/reference/cdialogimpl-class.md) als Basisklasse .  
  
> [!NOTE]
>  `CSimpleDialog`erstellt nur modale Dialogfelder, die nur die allgemeine Windows-Steuerelemente zu unterstützen. `CDialogImpl`erstellt entweder modal oder nicht modale Dialogfelder.  
  
### <a name="to-add-an-atl-dialog-resource-to-your-project"></a>Um dem Projekt eine ATL-Dialogfeldressource hinzufügen  
  
1.  Erstellen Sie eine ATL-Projekt mit der [ATL-Projektassistenten](../../atl/reference/atl-project-wizard.md).  
  
2.  Von [Klassenansicht](http://msdn.microsoft.com/en-us/8d7430a9-3e33-454c-a9e1-a85e3d2db925)mit der rechten Maustaste auf den Projektnamen, und klicken Sie auf **hinzufügen** aus dem Kontextmenü. Klicken Sie auf **Klasse hinzufügen**.  
  
3.  Im Bereich Vorlagen die [Klasse hinzufügen](../../ide/add-class-dialog-box.md) (Dialogfeld), klicken Sie auf **ATL-Dialogfeld**. Klicken Sie auf **öffnen** zum Anzeigen der [ATL-Dialogfeld-Assistent](../../atl/reference/atl-dialog-wizard.md).  
  
 Weitere Informationen finden Sie unter [Implementieren eines Dialogfelds](../../atl/implementing-a-dialog-box.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Hinzufügen einer Klasse](../../ide/adding-a-class-visual-cpp.md)   
 [Fensterklassen](../../atl/atl-window-classes.md)   
 [Meldungszuordnungen](../../atl/message-maps-atl.md)

