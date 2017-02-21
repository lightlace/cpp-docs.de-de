---
title: "CDumpContext Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CDumpContext"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AfxDump object"
  - "CDumpContext class"
  - "Diagnose, diagnostic classes"
  - "diagnostic classes"
  - "Diagnose, diagnostic classes"
ms.assetid: 98c52b2d-14b5-48ed-b423-479a4d1c60fa
caps.latest.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 22
---
# CDumpContext Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Unterstützung Stream\-ausgerichtete Diagnose ausgegeben in Form von Klartext.  
  
## Syntax  
  
```  
class CDumpContext  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CDumpContext::CDumpContext](../Topic/CDumpContext::CDumpContext.md)|Erstellt ein `CDumpContext`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CDumpContext::DumpAsHex](../Topic/CDumpContext::DumpAsHex.md)|Gibt das angegebene Element im Hexadezimalformat.|  
|[CDumpContext::Flush](../Topic/CDumpContext::Flush.md)|Leert alle Daten im Dumpkontextpuffer.|  
|[CDumpContext::GetDepth](../Topic/CDumpContext::GetDepth.md)|Ruft eine ganze Zahl entsprechend der Tiefe des Dumps ab.|  
|[CDumpContext::HexDump](../Topic/CDumpContext::HexDump.md)|Gibt die Bytes, die in einem Array im Hexadezimalformat enthalten sind.|  
|[CDumpContext::SetDepth](../Topic/CDumpContext::SetDepth.md)|Legt die Tiefe des Dumps fest.|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[CDumpContext::operator \<\<](../Topic/CDumpContext::operator%20%3C%3C.md)|Einfügungsvariablen und Objekte in den Dumpkontext.|  
  
## Hinweise  
 `CDumpContext` hat keine Basisklasse.  
  
 Sie können [afxDump](../Topic/afxDump%20\(CDumpContext%20in%20MFC\).md), ein predeclared `CDumpContext`\-Objekt verwenden, für die meisten des Sicherns.  Das Objekt `afxDump` ist nur in der Debugversion Microsoft Foundation Class\-Bibliothek verfügbar.  
  
 Mehrere der Arbeitsspeicher [Diagnosedienste](../../mfc/reference/diagnostic-services.md) Verwendung `afxDump` für ihre Ausgabe.  
  
 Mit der Windows\-Umgebung wird die Ausgabe des vordefinierten `afxDump`\-Objekt, dem ähnlich dem `cerr` Stream, an den Debugger über die Windows\-Funktion **OutputDebugString** weitergeleitet.  
  
 Die `CDumpContext`\-Klasse hat einen überladenen Operator Einfügen \(**\<\<**\) für `CObject` Zeiger, der die Daten des Objekts gespeichert wird.  Wenn Sie ein benutzerdefiniertes für Dumps für ein von abgeleitetes Objekt erfordern, überschreiben Sie [CObject::Dump](../Topic/CObject::Dump.md).  Die meisten Microsoft Foundations\-Klassen implementieren eine überschriebene `Dump`\-Memberfunktion.  
  
 Klassen, die nicht von `CObject`, wie `CString`, `CTime` und `CTimeSpan` abgeleitet werden, verfügen über eigene überladenen `CDumpContext` Einfügungsoperatoren, wie häufig benutzte Strukturen wie **CFileStatus**, `CPoint` und `CRect` ausführen.  
  
 Wenn Sie [IMPLEMENT\_DYNAMIC](../Topic/IMPLEMENT_DYNAMIC.md) oder [IMPLEMENT\_SERIAL](../Topic/IMPLEMENT_SERIAL.md)\-Makro in der Implementierung der Klasse verwenden, dann gibt `CObject::Dump` den Titel aus dem `CObject` von abgeleitete Klasse.  Andernfalls gibt sie `CObject`.  
  
 Die Klasse ist `CDumpContext` mit \- Debug\- und Releaseversionen der Bibliothek verfügbar, die `Dump`\-Memberfunktion ist nur in der Debugversion definiert.  Verwenden Sie **\#ifdef \_DEBUG** \/ `#endif`\-Anweisungen, um den Diagnosecode, einschließlich der benutzerdefinierten `Dump`\-Memberfunktionen zu markieren.  
  
 Bevor Sie ein eigenes `CDumpContext`\-Objekt erstellen, müssen Sie ein Objekt die `CFile` dient als das Dumpziel erstellen.  
  
 Weitere Informationen zu `CDumpContext`, finden Sie unter [Debuggen von MFC\-Anwendungen](../Topic/MFC%20Debugging%20Techniques.md).  
  
 **\#define \_DEBUG**  
  
## Vererbungshierarchie  
 `CDumpContext`  
  
## Anforderungen  
 **Header:**  afx.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CFile Class](../../mfc/reference/cfile-class.md)   
 [CObject Class](../../mfc/reference/cobject-class.md)