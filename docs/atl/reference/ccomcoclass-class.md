---
title: "CComCoClass Class"
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
  - "CComCoClass"
  - "ATL.CComCoClass"
  - "ATL::CComCoClass"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "aggregation [C++], aggregation models"
  - "CComCoClass class"
ms.assetid: 67cfefa4-8df9-47fa-ad58-2d1a1ae25762
caps.latest.revision: 19
caps.handback.revision: "8"
ms.author: "mblome"
manager: "ghogen"
---
# CComCoClass Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Diese Klasse enthält Methoden für Instanzen einer Klasse, und um seine Eigenschaften erstellen.  
  
## Syntax  
  
```  
  
      template<  
   class T,  
   const CLSID* pclsid = &CLSID_NULL  
>  
class CComCoClass  
```  
  
#### Parameter  
 `T`  
 Die Klasse, die von abgeleitet `CComCoClass`.  
  
 *pclsid*  
 Ein Zeiger auf CLSID des Objekts.  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CComCoClass::CreateInstance](../Topic/CComCoClass::CreateInstance.md)|\(Statisch\) erstellt eine Instanz der Klasse und der Abfragen für eine Schnittstelle.|  
|[CComCoClass::Error](../Topic/CComCoClass::Error.md)|\(Statisch\) bietet umfassende Fehlerinformationen an den Client zurück.|  
|[CComCoClass::GetObjectCLSID](../Topic/CComCoClass::GetObjectCLSID.md)|\(Statisch\) gibt die Klassen\-ID des Objekts zurück.|  
|[CComCoClass::GetObjectDescription](../Topic/CComCoClass::GetObjectDescription.md)|\(Statische\) überschreiben, um die Beschreibung des Objekts zurückzugeben.|  
  
## Hinweise  
 `CComCoClass` stellt Methoden zum Abrufen der CLSID eines Objekts, Festlegen von Fehlerinformationen und Erstellen von Instanzen der Klasse.  Alle Klasse registriertes in [Objektzuordnung](assetId:///b57619cc-534f-4b8f-bfd4-0c12f937202f) sollten von `CComCoClass` abgeleitet werden.  
  
 `CComCoClass` definiert auch die Standardklassenfactory und das Aggregationsmodell für das Objekt.  `CComCoClass` verwendet die folgenden zwei Makros:  
  
-   [DECLARE\_CLASSFACTORY](../Topic/DECLARE_CLASSFACTORY.md) deklariert die Klassenfactory, um [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) zu sein.  
  
-   [DECLARE\_AGGREGATABLE](../Topic/DECLARE_AGGREGATABLE.md) deklariert, dass das Objekt aggregiert werden kann.  
  
 Sie können einen dieser Vorgaben überschreiben, indem Sie ein anderes Makro in der Klassendefinition angeben.  Um beispielsweise [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md) anstelle `CComClassFactory` zu verwenden, geben Sie die [DECLARE\_CLASSFACTORY2](../Topic/DECLARE_CLASSFACTORY2.md)\-Makro an:  
  
 [!CODE [NVC_ATL_COM#2](../CodeSnippet/VS_Snippets_Cpp/NVC_ATL_COM#2)]  
  
## Anforderungen  
 **Header:**  möchten  
  
## Siehe auch  
 [Class Overview](../../atl/atl-class-overview.md)