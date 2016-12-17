---
title: "CPropExchange Class"
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
  - "CPropExchange"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Steuerelemente [MFC], OLE"
  - "CPropExchange-Klasse"
  - "OLE-Steuerelemente, Dauerhaftigkeit"
ms.assetid: ed872180-e770-4942-892a-92139d501fab
caps.latest.revision: 22
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# CPropExchange Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Unterstützt die Implementierung der Dauerhaftigkeit für die OLE\-Steuerelemente.  
  
## Syntax  
  
```  
class AFX_NOVTABLE CPropExchange  
```  
  
## Mitglieder  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CPropExchange::ExchangeBlobProp](../Topic/CPropExchange::ExchangeBlobProp.md)|Tauscht eine Eigenschaft des BLOB \(Binary Large Objects\) aus.|  
|[CPropExchange::ExchangeFontProp](../Topic/CPropExchange::ExchangeFontProp.md)|Tauscht eine Schriftarteigenschaft aus.|  
|[CPropExchange::ExchangePersistentProp](../Topic/CPropExchange::ExchangePersistentProp.md)|Tauscht eine Eigenschaft zwischen einem Steuerelement und einer Datei aus.|  
|[CPropExchange::ExchangeProp](../Topic/CPropExchange::ExchangeProp.md)|Tauscht integrierten Eigenschaften eines beliebigen Datentyps aus.|  
|[CPropExchange::ExchangeVersion](../Topic/CPropExchange::ExchangeVersion.md)|Tauscht die Versionsnummer eines OLE\-Steuerelements aus.|  
|[CPropExchange::GetVersion](../Topic/CPropExchange::GetVersion.md)|Ruft die Versionsnummer eines OLE\-Steuerelements ab.|  
|[CPropExchange::IsAsynchronous](../Topic/CPropExchange::IsAsynchronous.md)|Bestimmt, ob Eigenschaftaustausch asynchron durchgeführt werden.|  
|[CPropExchange::IsLoading](../Topic/CPropExchange::IsLoading.md)|Gibt an, ob Eigenschaften in das Steuerelement geladen oder von ihm gespeichert.|  
  
## Hinweise  
 `CPropExchange` hat keine Basisklasse.  
  
 Richtet den Kontext und die Richtung eines Eigenschaftaustausches ein.  
  
 Dauerhaftigkeit ist der Austausch der Zustandsinformationen des Steuerelements, normalerweise dargestellt durch seine Eigenschaften, zwischen dem Steuerelement selbst und einem mittleren.  
  
 Das Framework erstellt ein Objekt, das von `CPropExchange` abgeleitet wird, wenn es benachrichtigt wird, dass die Eigenschaften eines OLE\-Steuerelements von geladen werden oder permanenten Speicher gespeichert werden sollen.  
  
 Das Framework wird ein Zeiger auf diesem `CPropExchange`\-Objekt zu `DoPropExchange`\-Funktion des Steuerelements.  Wenn Sie einen Assistenten verwenden, um zu erstellen, werden der Starter für das Steuerelement, `DoPropExchange`\-Funktionsaufrufe `COleControl::DoPropExchange` des Steuerelements.  Die Basisklassenversion tauscht die Vorrateigenschaften des Steuerelements aus; Sie ändern die Version der abgeleitete Klasse, um Eigenschaften auszutauschen, die Sie dem Steuerelement hinzugefügt haben.  
  
 `CPropExchange` kann verwendet werden, um die Eigenschaften eines Steuerelements zu serialisieren oder die Eigenschaften eines Steuerelements nach der Auslastungs\- oder der Erstellung eines Steuerelements zu initialisieren.  Die `ExchangeProp` und `ExchangeFontProp`\-Memberfunktionen von `CPropExchange` sind in der Lage, Eigenschaften zu speichern und sie aus verschiedenen Medien zu laden.  
  
 Weitere Informationen zur Verwendung von `CPropExchange`, finden Sie im Artikel [MFC\-ActiveX\-Steuerelemente: Eigenschaftenseiten](../../mfc/mfc-activex-controls-property-pages.md).  
  
## Vererbungshierarchie  
 `CPropExchange`  
  
## Anforderungen  
 **Header:**  afxctl.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [COleControl::DoPropExchange](../Topic/COleControl::DoPropExchange.md)