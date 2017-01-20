---
title: "_U_MENUorID Class"
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
  - "ATL._U_MENUorID"
  - "ATL::_U_MENUorID"
  - "_U_MENUorID"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_U_MENUorID class"
  - "U_MENUorID class"
ms.assetid: cfc8032b-61b4-4a68-ba3a-92b82500ccae
caps.latest.revision: 20
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# _U_MENUorID Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt Wrapper für **CreateWindow** und **CreateWindowEx** bereit.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in der Windows Runtime ausführen.  
  
## Syntax  
  
```  
  
class _U_MENUorID  
  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[\_U\_MENUorID::\_U\_MENUorID](../Topic/_U_MENUorID::_U_MENUorID.md)|Der \-Konstruktor.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[\_U\_MENUorID::m\_hMenu](../Topic/_U_MENUorID::m_hMenu.md)|Ein Handle zu einem Menü.|  
  
## Hinweise  
 Diese Argumentadapterklasse können entweder **UINT** IDs \(s\) oder die an eine Funktion übergeben werden Menühandles `HMENU`\(s\), ohne eine explizite Umwandlung erforderlich vonseiten des Aufrufers.  
  
 Diese Klasse ist für das Implementieren von Wrappern zu den [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) und [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680)\-Funktionen der Windows\-API, insbesondere entwickelt, die `HMENU` akzeptieren ein Argument, das ein Bezeichner des untergeordneten MDI\-Fensters \(**UINT**\) und nicht werden, wann ein Menühandle ist.  Beispielsweise können Sie diese Klasse als Parameter zu [CWindowImpl::Create](../Topic/CWindowImpl::Create.md) in Verwendung finden.  
  
 Die Klasse definiert zwei Konstruktorüberladungen: Sie akzeptiert ein **UINT**\-Argument und der andere akzeptiert ein `HMENU`\-Argument.  Das **UINT**\-Argument wird nur für `HMENU` im Konstruktor und im Ergebnis umgewandelt, die im Einzelnen Datenmember der Klasse, [m\_hMenu](../Topic/_U_MENUorID::m_hMenu.md) gespeichert werden.  Das Argument in `HMENU`\-Konstruktor wird direkt ohne Konvertierung gespeichert.  
  
## Anforderungen  
 **Header:**  atlwin.h  
  
## Siehe auch  
 [Class Overview](../../atl/atl-class-overview.md)