---
title: "CDialogBar Class"
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
  - "CDialogBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDialogBar class"
  - "dialog bars, Windows modeless dialog box"
  - "Dialogfelder, Nicht modal"
ms.assetid: da2f7a30-970c-44e3-87f0-6094bd002cab
caps.latest.revision: 23
caps.handback.revision: "12"
ms.author: "mblome"
manager: "ghogen"
---
# CDialogBar Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Stellt die Funktionalität eines Windows\-nichtmodal Dialogfeld in einer Steuerleiste bereit.  
  
## Syntax  
  
```  
class CDialogBar : public CControlBar  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CDialogBar::CDialogBar](../Topic/CDialogBar::CDialogBar.md)|Erstellt ein `CDialogBar`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CDialogBar::Create](../Topic/CDialogBar::Create.md)|Erstellt eine Windows\-Dialogleiste und fügt sie dem `CDialogBar`\-Objekt.|  
  
## Hinweise  
 Eine Dialogleiste ähnelt einem Dialogfeld darin, dass sie Standardwindows\-steuerelemente enthält, die der Benutzer zwischen mit der TAB\-TASTE kann.  Eine andere Ähnlichkeit ist, dass Sie eine Dialogfeldvorlage erstellen, um die Dialogleiste darzustellen.  
  
 Eine Dialogleiste zu erstellen und die Anwendung ist zum Erstellen und Verwenden eines Objekts `CFormView` ähnlich.  Zunächst verwenden Sie [Dialog\-Editor](../../mfc/dialog-editor.md), um eine Dialogfeldvorlage mit dem Format **WS\_CHILD** und kein anderes Format zu definieren.  Die Vorlage darf das Format **WS\_VISIBLE** aufweisen.  Verwenden Sie im Anwendungscode rufen Sie den Konstruktor auf, um das `CDialogBar`\-Objekt zu erstellen, und rufen Sie dann **Create** auf, um das Dialogleistenfenster zu erstellen und auf den `CDialogBar`\-Objekt anzufügen.  
  
 Weitere Informationen zu `CDialogBar`, finden Sie im Artikel [Dialogleisten](../../mfc/dialog-bars.md) und [Technischer Hinweis 31](../../mfc/tn031-control-bars.md), Steuerleisten.  
  
> [!NOTE]
>  In der aktuellen Version kann ein `CDialogBar`\-Objekt keine Windows Forms\-Steuerelemente hosten.  Weitere Informationen über Windows Forms\-Steuerelemente in Visual C\+\+, finden Sie unter [Verwenden eines Windows Form\-Benutzersteuerelements in MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CControlBar](../../mfc/reference/ccontrolbar-class.md)  
  
 `CDialogBar`  
  
## Anforderungen  
 **Header:**  afxext.h  
  
## Siehe auch  
 [CTRLBARS MFC\-Beispiel](../../top/visual-cpp-samples.md)   
 [CControlBar Class](../../mfc/reference/ccontrolbar-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CFormView Class](../../mfc/reference/cformview-class.md)   
 [CControlBar Class](../../mfc/reference/ccontrolbar-class.md)