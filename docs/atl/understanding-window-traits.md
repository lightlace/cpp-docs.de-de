---
title: "Understanding Window Traits | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "window traits"
ms.assetid: c90cf850-9e91-49da-9cf3-ad4efb30347d
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Understanding Window Traits
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Fenstermerkmalklassen stellen eine einfache Methode für die Normung der Formate bereit, die für die Erstellung eines ATL\-Fensterobjekts verwendet werden.  Fenstermerkmale werden als Vorlagenparameter durch [CWindowImpl](../atl/reference/cwindowimpl-class.md) und andere ATL\-Fensterklassen als Methode zum Bereitstellen von standardmäßigen Fensterstilen auf Klassenebene akzeptiert.  
  
 Wenn der Ersteller einer Fensterinstanz Explizites im Aufruf von nicht [Erstellen Sie](../Topic/CWindowImpl::Create.md) bereitstellt, können Sie eine Merkmalklasse verwenden, um sicherzustellen, dass das Fenster weiterhin mit den richtigen Formaten erstellt wird.  Sie können sogar sicherstellen, dass bestimmte Formate für alle Instanzen dieser Fensterklasse beim Ermöglichen anderer Formate, pro Instanz festgelegt werden festgelegt werden.  
  
## ATL\-Fenster\-Merkmals\-Vorlagen  
 ATL stellt zwei Fenstermerkmalsvorlagen, die Sie an den festgelegten Standardstilen zur Kompilierzeit mithilfe ihrer Vorlagenparameter ermöglichen.  
  
|Klasse|Description|  
|------------|-----------------|  
|[CWinTraits](../atl/reference/cwintraits-class.md)|Verwenden Sie diese Vorlage, wenn Sie standardmäßige Fensterstile bereitstellen möchten, die nur verwendet werden, wenn keine anderen Formate im Aufruf von **Create** angegeben werden.  Die Formate haben zur Laufzeit haben Vorrang vor den Formaten bereit, die zur Kompilierzeit festgelegt wurden.|  
|[CWinTraitsOR](../atl/reference/cwintraitsor-class.md)|Verwenden Sie diese Klasse, wenn Sie Stile angeben möchten, die für die Fensterklasse immer festgelegt werden müssen.  Die Formate haben zur Laufzeit kombiniert werden mit den Formaten bereit, die zur Kompilierzeit mithilfe des bitweisen OR\-Operators festgelegt wurden.|  
  
 Zusätzlich zu diesen Vorlagen ATL stellt einige vordefinierte Spezialisierungen der `CWinTraits` Vorlage für häufig verwendete Kombinationen von Fensterstilen bereit.  Siehe die [CWinTraits](../atl/reference/cwintraits-class.md)\-Referenzdokumentation für vollständige Details.  
  
## Benutzerdefinierte Fenster\-Merkmale  
 In der unwahrscheinlichen Fall, die, eine der Vorlagen zu spezialisieren, die von ATL bereitgestellt werden, nicht ausreichend ist und Sie eine eigene Merkmalklasse erstellen müssen, müssen Sie eine Klasse erstellen, die zwei statische Funktionen implementiert: `GetWndStyle` und **GetWndStyleEx**:  
  
 [!CODE [NVC_ATL_Windowing#68](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_Windowing#68)]  
  
 Jede dieser Funktionen wird leicht Formatwert zur Laufzeit übergeben, den es verwenden kann, um einen neuen Formatwert zu erzeugen.  Wenn die Fenstermerkmalklasse als Vorlagenargument zu einer ATL\-Fensterklasse verwendet wird, haben die Formatwerte zu diesen statischen Funktionen sind, was als die Formatargumente zu [Erstellen Sie](../Topic/CWindowImpl::Create.md) übergeben wurde.  
  
## Siehe auch  
 [Fensterklassen](../atl/atl-window-classes.md)