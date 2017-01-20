---
title: "CCachedDataPathProperty Class"
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
  - "CCachedDataPathProperty"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX-Steuerelemente [C++], Asynchron"
  - "asynchronous controls [C++]"
  - "CCachedDataPathProperty class"
  - "memory files [C++]"
  - "OLE-Steuerelemente [C++], Asynchron"
ms.assetid: 0d81356b-4fe5-43f6-aed2-2eb5a5485706
caps.latest.revision: 22
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# CCachedDataPathProperty Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implementiert eine OLE\-Steuerelement\-Eigenschaft übertrug asynchron und zwischengespeichert in einer Arbeitsspeicherdatei.  
  
## Syntax  
  
```  
class CCachedDataPathProperty : public CDataPathProperty  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CCachedDataPathProperty::CCachedDataPathProperty](../Topic/CCachedDataPathProperty::CCachedDataPathProperty.md)|Erstellt ein `CCachedDataPathProperty`\-Objekt.|  
  
### Öffentliche Datenmember  
  
|Name|Beschreibung|  
|----------|------------------|  
|[CCachedDataPathProperty::m\_Cache](../Topic/CCachedDataPathProperty::m_Cache.md)|`CMemFile` in dem Objekt, um Daten zwischenzuspeichern.|  
  
## Hinweise  
 Eine Arbeitsspeicherdatei wird in RAM statt auf dem Datenträger gespeichert und zur schnellen temporäre Übertragungen hilfreich.  
  
 Zusammen mit **CAysncMonikerFile** und `CDataPathProperty` stellt `CCachedDataPathProperty`\-Funktionen für die Verwendung von asynchronen Monikern in den OLE\-Steuerelementen bereit.  Mit `CCachedDataPathProperty`\-Objekten sind Sie für Datenübertragung asynchron von einer URL in der Lage Datei oder Quelle und speichern sie in einer Arbeitsspeicherdatei über die `m_Cache` Öffentlichkeitsvariable.  Alle Daten werden in der Arbeitsspeicherdatei gespeichert, und es besteht keine Notwendigkeit, [OnDataAvailable](../Topic/CAsyncMonikerFile::OnDataAvailable.md) überschreiben, es sei denn, Sie für Benachrichtigungen überwachen und darauf reagieren möchten.  Wenn Sie eine große GIF\-Datei übertragen und das Steuerelement benachrichtigen möchten, dass mehr Daten angekommen sind und es sich neu entwerfen soll, überschreiben `OnDataAvailable`, um die Benachrichtigung zu machen.  
  
 Die `CCachedDataPathProperty`\-Klasse wird von `CDataPathProperty` abgeleitet.  
  
 Weitere Informationen dazu, wie asynchrone Moniker und ActiveX\-Steuerelemente in Internetanwendungen, finden Sie in den folgenden Themen:  
  
-   [Internet\-erste Schritte: ActiveX\-Steuerelemente](../../mfc/activex-controls-on-the-internet.md)  
  
-   [Internet\-erste Schritte: Asynchrone Moniker](../../mfc/asynchronous-monikers-on-the-internet.md)  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [Die C\-Datei](../../mfc/reference/cfile-class.md)  
  
 [COleStreamFile](../../mfc/reference/colestreamfile-class.md)  
  
 [CMonikerFile](../../mfc/reference/cmonikerfile-class.md)  
  
 [CAsyncMonikerFile](../../mfc/reference/casyncmonikerfile-class.md)  
  
 [CDataPathProperty](../../mfc/reference/cdatapathproperty-class.md)  
  
 `CCachedDataPathProperty`  
  
## Anforderungen  
 **Header:** afxctl.h  
  
## Siehe auch  
 [CDataPathProperty Class](../../mfc/reference/cdatapathproperty-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CDataPathProperty Class](../../mfc/reference/cdatapathproperty-class.md)