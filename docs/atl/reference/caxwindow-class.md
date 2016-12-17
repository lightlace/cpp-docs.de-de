---
title: "CAxWindow Class"
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
  - "CAxWindowT"
  - "CAxWindow"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ATL, Hosting von ActiveX-Steuerelementen"
  - "CAxWindow class"
ms.assetid: 85e79261-43e4-4770-bde0-1ff87f222b0f
caps.latest.revision: 24
caps.handback.revision: "12"
ms.author: "mblome"
manager: "ghogen"
---
# CAxWindow Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt Methoden zum Bearbeiten eines Fensters ein ActiveX\-Steuerelement hosten\) bereit.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in der Windows Runtime ausführen.  
  
## Syntax  
  
```  
  
class CAxWindow : public CWindow  
  
```  
  
## Mitglieder  
  
### Methoden  
  
|||  
|-|-|  
|[AttachControl](../Topic/CAxWindow::AttachControl.md)|Fügt ein vorhandenes ActiveX\-Steuerelement zum `CAxWindow`\-Objekt.|  
|[CAxWindow](../Topic/CAxWindow::CAxWindow.md)|Erstellt ein `CAxWindow`\-Objekt.|  
|[CreateControl](../Topic/CAxWindow::CreateControl.md)|Erstellt ein ActiveX\-Steuerelement, initialisiert und hostet `CAxWindow` es im Fenster.|  
|[CreateControlEx](../Topic/CAxWindow::CreateControlEx.md)|Erstellt ein ActiveX\-Steuerelement und ruft einen Schnittstellenzeiger \(oder Zeiger\) aus dem Steuerelement ab.|  
|[GetWndClassName](../Topic/CAxWindow::GetWndClassName.md)|\(Statisch\) ruft den vordefinierten Klassennamen des `CAxWindow`\-Objekts ab.|  
|[QueryControl](../Topic/CAxWindow::QueryControl.md)|Ruft **IUnknown** des gehosteten ActiveX\-Steuerelements ab.|  
|[QueryHost](../Topic/CAxWindow::QueryHost.md)|Ruft den **IUnknown** Zeiger `CAxWindow` des Objekts ab.|  
|[SetExternalDispatch](../Topic/CAxWindow::SetExternalDispatch.md)|Legt die externe Dispatchschnittstelle ab, die durch das `CAxWindow`\-Objekt verwendet wird.|  
|[SetExternalUIHandler](../Topic/CAxWindow::SetExternalUIHandler.md)|Legt die externe **IDocHostUIHandler**\-Schnittstelle ab, die durch das `CAxWindow`\-Objekt verwendet wird.|  
  
### Operatoren  
  
|||  
|-|-|  
|[Operator \=](../Topic/CAxWindow::operator%20=.md)|Weist **HWND**  zu einem vorhandenen **CAxWindow**\-Objekt zu.|  
  
## Hinweise  
 Diese Klasse stellt Methoden zum Bearbeiten eines Fensters bereit, das ein ActiveX\-Steuerelement hostet.  Das Hosting wird von "**AtlAxWin80"** bereitgestellt, das von `CAxWindow` umschlossen wird.  
  
 \- Klasse `CAxWindow` wird als Spezialisierung der `CAxWindowT`\-Klasse implementiert.  Diese Spezialisierung wird als deklariert:  
  
 `typedef CAxWindowT<CWindow> CAxWindow;`  
  
 Wenn Sie die Basisklasse ändern müssen, können Sie `CAxWindowT` verwenden und die neue Basisklasse als Vorlagenargument angeben.  
  
## Anforderungen  
 **Header:** atlwin.h  
  
## Siehe auch  
 [ATLCON\-Beispiel](../../top/visual-cpp-samples.md)   
 [CWindow Class](../../atl/reference/cwindow-class.md)   
 [Grundlagen von zusammengesetzten Steuerelementen](../../atl/atl-composite-control-fundamentals.md)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [Fragen und Antworten zur Steuerelementkapselung](../../atl/atl-control-containment-faq.md)