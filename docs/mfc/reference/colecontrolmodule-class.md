---
title: "COleControlModule Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleControlModule"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleControlModule class"
  - "control modules"
  - "MFC ActiveX controls, OLE control modules"
  - "OLE control modules"
ms.assetid: 0721724d-d4af-4eda-ad34-5a2b27810dd4
caps.latest.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# COleControlModule Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Basisklasse, von der Sie ein OLE\-Steuerelement\-Modulobjekt berechnen.  
  
## Syntax  
  
```  
class COleControlModule : public CWinApp  
```  
  
## Hinweise  
 Diese Klasse stellt Memberfunktionen für das Initialisieren der Steuereinheit bereit.  Jedes OLE\-Steuerelement\-Modul, das die Microsoft Foundations\-Klassen verwendet, kann ein Objekt nur enthalten, das von `COleControlModule` abgeleitet wird.  Dieses Objekt wird erstellt, wenn andere globale Objekte C\+\+ erstellt wurden.  Deklarieren Sie das `COleControlModule` abgeleitetes Objekt auf globaler Ebene.  
  
 Weitere Informationen zur Verwendung der `COleControlModule`\-Klasse, finden Sie unter [CWinApp](../../mfc/reference/cwinapp-class.md) die Klasse und den Artikel [ActiveX\-Steuerelemente](../../mfc/mfc-activex-controls.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWinThread](../../mfc/reference/cwinthread-class.md)  
  
 [CWinApp](../../mfc/reference/cwinapp-class.md)  
  
 `COleControlModule`  
  
## Anforderungen  
 **Header:**  afxctl.h  
  
## Siehe auch  
 [MFC\-Beispiel TESTHELP](../../top/visual-cpp-samples.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)