---
title: "CAxWindow2T Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::CAxWindow2T<TBase>"
  - "ATL::CAxWindow2T"
  - "CAxWindow2T"
  - "ATL.CAxWindow2T<TBase>"
  - "ATL.CAxWindow2T"
  - "CAxWindow2"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CAxWindow2 class"
ms.assetid: b87bc943-7991-4537-b902-2138d7f4d837
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# CAxWindow2T Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse stellt Methoden zum Bearbeiten eines Fensters, das ein ActiveX\-Steuerelement hostet, und unterstützt auch das Hosten von lizenzierten ActiveX\-Steuerelemente.  
  
> [!IMPORTANT]
>  Diese Klasse und ihre Member können in Anwendungen nicht verwendet werden, die in der Windows Runtime ausführen.  
  
## Syntax  
  
```  
  
      template <   
class TBase= CWindow   
>  
class CAxWindow2T :   
public CAxWindowT< TBase >  
```  
  
#### Parameter  
 *TBase*  
 Die Klasse, von der `CAxWindowT` abgeleitet.  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CAxWindow2T::CAxWindow2T](../Topic/CAxWindow2T::CAxWindow2T.md)|Erstellt ein `CAxWindow2T`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CAxWindow2T::Create](../Topic/CAxWindow2T::Create.md)|Stellt ein Hostfenster erstellt.|  
|[CAxWindow2T::CreateControlLic](../Topic/CAxWindow2T::CreateControlLic.md)|Erstellt ein lizenziertes ActiveX\-Steuerelement, initialisiert und hostet es im angegebenen Fenster.|  
|[CAxWindow2T::CreateControlLicEx](../Topic/CAxWindow2T::CreateControlLicEx.md)|Erstellt ein lizenziertes ActiveX\-Steuerelement, initialisiert, hostet es im angegebenen Fenster und ruft einen Schnittstellenzeiger \(oder Zeiger\) aus dem Steuerelement ab.|  
|[CAxWindow2T::GetWndClassName](../Topic/CAxWindow2T::GetWndClassName.md)|Statische Methode, die den Namen der Fensterklasse abruft.|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[CAxWindow2T::operator \=](../Topic/CAxWindow2T::operator%20=.md)|Weist `HWND` zu einem vorhandenen `CAxWindow2T`\-Objekt zu.|  
  
## Hinweise  
 `CAxWindow2T` stellt Methoden zum Bearbeiten eines Fensters bereit, das ein ActiveX\-Steuerelement hostet.  `CAxWindow2T` unterstützt auch das Hosten von lizenzierten ActiveX\-Steuerelemente.  Das Hosting wird von "**AtlAxWinLic80**" bereitgestellt, das von `CAxWindow2T` umschlossen wird.  
  
 \- Klasse `CAxWindow2` wird als Spezialisierung der `CAxWindow2T`\-Klasse implementiert.  Diese Spezialisierung wird als deklariert:  
  
 `typedef CAxWindow2T <CWindow> CAxWindow2;`  
  
> [!NOTE]
>  `CAxWindowT`\-Member werden unter [CAxWindow](../../atl/reference/caxwindow-class.md) dokumentiert.  
  
 Siehe [Hosten von ActiveX\-Steuerelementen mit ATL AXHost](../../atl/hosting-activex-controls-using-atl-axhost.md) für ein Beispiel, das die Member dieser Klasse verwendet.  
  
## Vererbungshierarchie  
 `TBase`  
  
 `CAxWindowT`  
  
 `CAxWindow2T`  
  
## Anforderungen  
 **Header:**  atlwin.h  
  
## Siehe auch  
 [Class Overview](../../atl/atl-class-overview.md)   
 [Fragen und Antworten zur Steuerelementkapselung](../../atl/atl-control-containment-faq.md)