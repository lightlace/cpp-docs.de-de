---
title: "CSimpleDialog Class"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "reference"
f1_keywords: 
  - "ATL::CSimpleDialog"
  - "CSimpleDialgo"
  - "CSimpleDialog"
  - "ATL.CSimpleDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSimpleDialog class"
  - "CSimpleDialog class, modal dialog boxes in ATL"
  - "Dialogfelder, Modal"
  - "Modale Dialogfelder, ATL"
ms.assetid: 2ae65cc9-4f32-4168-aecd-200b4a480fdf
caps.latest.revision: 19
caps.handback.revision: "7"
ms.author: "mblome"
manager: "ghogen"
---
# CSimpleDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse implementiert ein einfaches modales Dialogfeld.  
  
## Syntax  
  
```  
  
      template <  
   WORD t_wDlgTemplateID,  
   BOOL t_bCenter = TRUE  
>  
class CSimpleDialog :  
   public CDialogImplBase  
```  
  
#### Parameter  
 *t\_wDlgTemplateID*  
  
 Das Ressourcen\-ID der Dialogfeldvorlagen\-Ressource.  
  
 *t\_bCenter*  
 **TRUE**, wenn das gleichzeitig auf dem Besitzerfenster zentriert werden soll; andernfalls **FALSE**.  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CSimpleDialog::DoModal](../Topic/CSimpleDialog::DoModal.md)|Stellt ein modales Dialogfeld erstellt.|  
  
## Hinweise  
 Implementiert ein modales Dialogfeld mit grundlegenden Funktionalität.  `CSimpleDialog` unterstützt nur allgemeine Windows\-Steuerelemente.  Um ein modales Dialogfeld zu erstellen und anzuzeigen, erstellen Sie eine Instanz dieser Klasse und den Namen einer vorhandenen Ressourcenvorlage für das Dialogfeld angeben.  Das Dialogfeldobjekt wird abgeschlossen, wenn der Benutzer auf jedes Steuerelement mit einem vordefinierten Wert klickt \(z IDOK oder IDCANCEL\).  
  
 `CSimpleDialog` ermöglicht es Ihnen, nur modale Dialogfelder zu erstellen.  `CSimpleDialog` sieht die Dialogfeldprozedur vor, die die Standardmeldungszuordnung verwendet, um Meldungen auf die entsprechenden Handler zu verweisen.  
  
 Siehe [Implementieren eines Dialogfelds](../../atl/implementing-a-dialog-box.md) weitere Informationen.  
  
## Vererbungshierarchie  
 `CDialogImplBase`  
  
 `CSimpleDialog`  
  
## Anforderungen  
 **Header:**  atlwin.h  
  
## Siehe auch  
 [Class Overview](../../atl/atl-class-overview.md)