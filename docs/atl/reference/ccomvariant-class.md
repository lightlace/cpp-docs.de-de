---
title: "CComVariant Class"
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
  - "ATL.CComVariant"
  - "ATL::CComVariant"
  - "CComVariant"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComVariant class"
  - "VARIANT macro"
  - "VARIANT macro, ATL"
ms.assetid: 4d31149c-d005-44b5-a509-10f84afa2b61
caps.latest.revision: 26
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# CComVariant Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse umschließt den `VARIANT`\-Typ ein und stellt einen Member bereit, der den Typ von den gespeicherten Daten angibt.  
  
## Syntax  
  
```  
  
class CComVariant : public tagVARIANT  
  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CComVariant::CComVariant](../Topic/CComVariant::CComVariant.md)|Der \-Konstruktor.|  
|[CComVariant::~CComVariant](../Topic/CComVariant::~CComVariant.md)|Der Destruktor.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CComVariant::Attach](../Topic/CComVariant::Attach.md)|Fügt **VARIANT** zum `CComVariant`\-Objekt.|  
|[CComVariant::ChangeType](../Topic/CComVariant::ChangeType.md)|Konvertiert das `CComVariant`\-Objekt zu einem neuen Typ.|  
|[CComVariant::Clear](../Topic/CComVariant::Clear.md)|Löscht das `CComVariant`\-Objekt.|  
|[CComVariant::Copy](../Topic/CComVariant::Copy.md)|Kopiert **VARIANT** zum `CComVariant`\-Objekt.|  
|[CComVariant::CopyTo](../Topic/CComVariant::CopyTo.md)|Kopiert den Inhalt des `CComVariant`\-Objekts.|  
|[CComVariant::Detach](../Topic/CComVariant::Detach.md)|Trennt zugrunde liegende **VARIANT** vom `CComVariant`\-Objekt.|  
|[CComVariant::GetSize](../Topic/CComVariant::GetSize.md)|Gibt die Größe in Anzahl von Bytes des Inhalts des `CComVariant`\-Objekts zurück.|  
|[CComVariant::ReadFromStream](../Topic/CComVariant::ReadFromStream.md)|Lädt **VARIANT** aus einem Stream.|  
|[CComVariant::SetByRef](../Topic/CComVariant::SetByRef.md)|Initialisiert das Objekt `CComVariant` und legt den **vt**\-Member zu **VT\_BYREF** fest.|  
|[CComVariant::WriteToStream](../Topic/CComVariant::WriteToStream.md)|Rettet zugrunde liegende **VARIANT** in einem Stream.|  
  
### Öffentliche Operatoren  
  
|||  
|-|-|  
|[CComVariant::operator \<](../Topic/CComVariant::operator%20%3C.md)|Gibt an, ob das angegebene Objekt `CComVariant` kleiner als **VARIANT** ist.|  
|[CComVariant::operator \>](../Topic/CComVariant::operator%20%3E.md)|Gibt an, ob das angegebene Objekt `CComVariant` größer als **VARIANT** ist.|  
|[Operator\! \=](../Topic/CComVariant::operator%20!=.md)|Gibt an, ob das Objekt `CComVariant` nicht angegebenen **VARIANT** entspricht.|  
|[Operator \=](../Topic/CComVariant::operator%20=.md)|Weist einen Wert an den `CComVariant`\-Objekt zu.|  
|[Operator \=\=](../Topic/CComVariant::operator%20==.md)|Gibt an, ob das Objekt `CComVariant` angegebenen **VARIANT** entspricht.|  
  
## Hinweise  
 `CComVariant` bindet den `VARIANT and VARIANTARG`\-Typ ein, der zu einer Union und einem Member besteht, die den Typ der Daten angibt, die in der Union gespeichert werden.  **VARIANT** s werden in der Regel in der Automatisierung verwendet.  
  
 `CComVariant` abgeleitet vom Typ **VARIANT**, sodass er verwendet werden, auf dem **VARIANT** verwendet werden kann.  Sie können das **V\_VT**\-Makro beispielsweise verwenden, um den Typ von `CComVariant` zu extrahieren, oder Sie können das **vt**\-Member direkt verweisen, wie Sie mit **VARIANT** können.  
  
## Vererbungshierarchie  
 `tagVARIANT`  
  
 `CComVariant`  
  
## Anforderungen  
 **Header:**  atlcomcli.h  
  
## Siehe auch  
 [Class Overview](../../atl/atl-class-overview.md)