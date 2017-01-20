---
title: "CArchive Class"
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
  - "CArchive"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CArchive class"
  - "data storage [C++], CArchive class"
  - "I/O [MFC], archiving objects"
  - "Serialisierung [C++], CArchive class"
  - "storage [C++], CArchive class"
ms.assetid: 9e950d23-b874-456e-ae4b-fe00781a7699
caps.latest.revision: 21
caps.handback.revision: "11"
ms.author: "mblome"
manager: "ghogen"
---
# CArchive Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ermöglicht es Ihnen, ein komplexes Netzwerk von Objekten in einer permanenten binären Form \(normalerweise Festplattenspeicher\) sichern die weiter besteht, nachdem diese Objekte gelöscht wurden.  
  
## Syntax  
  
```  
class CArchive  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CArchive::CArchive](../Topic/CArchive::CArchive.md)|Erstellt ein `CArchive`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CArchive::Abort](../Topic/CArchive::Abort.md)|Schließt ein Archiv, ohne eine Ausnahme auszulösen.|  
|[CArchive::Close](../Topic/CArchive::Close.md)|Leert ungeschriebene Daten und Trennungen von `CFile`.|  
|[CArchive::Flush](../Topic/CArchive::Flush.md)|Ungeschriebene Daten des Leerens vom Archivpuffer.|  
|[CArchive::GetFile](../Topic/CArchive::GetFile.md)|Ruft den `CFile`\-Objektzeiger für dieses Archiv ab.|  
|[CArchive::GetObjectSchema](../Topic/CArchive::GetObjectSchema.md)|Aufgerufen aus der `Serialize`\-Funktion, um die Version des Objekts zu bestimmen, das deserialisiert wird.|  
|[CArchive::IsBufferEmpty](../Topic/CArchive::IsBufferEmpty.md)|Bestimmt, ob der Puffer während Windows Sockets empfangen Prozess geleert wurde.|  
|[CArchive::IsLoading](../Topic/CArchive::IsLoading.md)|Bestimmt, ob das Archiv lädt.|  
|[CArchive::IsStoring](../Topic/CArchive::IsStoring.md)|Bestimmt, ob das Archiv speichert.|  
|[CArchive::MapObject](../Topic/CArchive::MapObject.md)|Setzt Objekte in der Zuordnung, die nicht zur Datei serialisiert werden, aber die verfügbar sind, damit Unterobjekte verweisen.|  
|[CArchive::Read](../Topic/CArchive::Read.md)|Liest unformatierte Bytes.|  
|[CArchive::ReadClass](../Topic/CArchive::ReadClass.md)|Liest einen Klassenverweis, der zuvor mit `WriteClass` gespeichert wird.|  
|[CArchive::ReadObject](../Topic/CArchive::ReadObject.md)|Ruft `Serialize`\-Funktion eines Objekts zum Laden auf.|  
|[CArchive::ReadString](../Topic/CArchive::ReadString.md)|Liest eine einzelne Textzeile.|  
|[CArchive::SerializeClass](../Topic/CArchive::SerializeClass.md)|Liest oder schreibt den Klassenverweis zum `CArchive`\-Objekt abhängig von der Richtung `CArchive`.|  
|[CArchive::SetLoadParams](../Topic/CArchive::SetLoadParams.md)|Legt die Größe fest, auf die das Lastarray vergrößert.  Muss aufgerufen werden, bevor ein Objekt geladen wird, oder bevor `MapObject` oder `ReadObject` aufgerufen wird.|  
|[CArchive::SetObjectSchema](../Topic/CArchive::SetObjectSchema.md)|Legt das Objektschema fest, das im Archivobjekt gespeichert wird.|  
|[CArchive::SetStoreParams](../Topic/CArchive::SetStoreParams.md)|Legt die Hashtabellengröße und die Blockgröße der Zuordnung fest, die verwendet wird, um eindeutige Objekte während des Serialisierungsprozesses zu identifizieren.|  
|[CArchive::Write](../Topic/CArchive::Write.md)|Schreibt unformatierte Bytes.|  
|[CArchive::WriteClass](../Topic/CArchive::WriteClass.md)|Schreibt `CArchive` einen Verweis auf `CRuntimeClass`.|  
|[CArchive::WriteObject](../Topic/CArchive::WriteObject.md)|Ruft `Serialize`\-Funktion eines Objekts zum Speichern auf.|  
|[CArchive::WriteString](../Topic/CArchive::WriteString.md)|Schreibt eine einzelne Textzeile.|  
  
### Öffentliche Operatoren  
  
|Name|Description|  
|----------|-----------------|  
|[CArchive::operator \<\<](../Topic/CArchive::operator%20%3C%3C.md)|Speicherobjekte und \-primitive Typen zum Archiv.|  
|[CArchive::operator \>\>](../Topic/CArchive::operator%20%3E%3E.md)|Lastobjekte und \-primitive Typen vom Archiv.|  
  
### Öffentliche Datenmember  
  
|Name|Description|  
|----------|-----------------|  
|[CArchive::m\_pDocument](../Topic/CArchive::m_pDocument.md)||  
  
## Hinweise  
 `CArchive` hat keine Basisklasse.  
  
 Später können Sie die Objekte im permanenten Speicher laden und diese im Arbeitsspeicher erneut erstellen.  Dieser Prozess gehindert Daten erhalten wird aufgerufen "Serialisierung".  
  
 Sie können sich ein Archivobjekt als Art Binärstream vorstellen.  Wie ein Eingabe\/Ausgabe\-Stream wird ein Archiv mit einer Datei zugeordnet und die gepufferte das Schreiben und Lesen von Daten nach und von Speicher zulässt.  Prozessfolgen eines Eingabe\/Ausgabe\-Streams von ASCII\-Zeichen, aber ein Archiv verarbeitet binäre Objektdaten in einem effizienten, nonredundant Format.  
  
 Sie müssen ein [Die C\-Datei](../../mfc/reference/cfile-class.md)\-Objekt erstellen, bevor Sie ein `CArchive`\-Objekt erstellen können.  Außerdem müssen Sie sicherstellen, dass der Methoden\/Speicherstatus des Archivs mit dem geöffneten Modus der Datei kompatibel ist.  Sie werden auf einen aktiven Archiv pro Datei beschränkt.  
  
 Wenn Sie ein `CArchive`\-Objekt erstellen, es zu einem Objekt der Klasse `CFile` an \(oder der abgeleiteten Klasse\) die eine geöffnete Datei darstellt.  Sie geben auch an, ob das Archiv zum Laden oder Speichern verwendet wird.  Ein Objekt, `CArchive` kann nicht nur primitive Typen verarbeiten jedoch gilt auch von den von [CObject](../../mfc/reference/cobject-class.md) abgeleiteten Klassen, für die Serialisierung entworfen wurden.  Eine serialisierbare Klasse ist normalerweise eine `Serialize`\-Memberfunktion, und verwendet normalerweise die [DECLARE\_SERIAL](../Topic/DECLARE_SERIAL.md) und [IMPLEMENT\_SERIAL](../Topic/IMPLEMENT_SERIAL.md)\-Makros, wie unter Klasse `CObject` beschrieben.  
  
 Die überladenen Operatoren der Extraktion \(**\>\>**\) und Einfügen \(**\<\<**\) sind Programmierung Schnittstellen des einfachen Archivs, die primitive Typen und `CObject` von abgeleitete Klassen unterstützen.  
  
 `CArchive` unterstützt auch Programmieren mit den MFC\-WindowsSocket\-Klassen [CSocket](../../mfc/reference/csocket-class.md) und [CSocketFile](../../mfc/reference/csocketfile-class.md).  Die [IsBufferEmpty](../Topic/CArchive::IsBufferEmpty.md)\-Memberfunktionsunterstützung die Verwendung.  
  
 Weitere Informationen zu `CArchive`, finden Sie in Artikel [Serialisierung](../../mfc/serialization-in-mfc.md) und [Windows Sockets: Verwenden von Sockets mit Archiven](../../mfc/windows-sockets-using-sockets-with-archives.md).  
  
## Vererbungshierarchie  
 `CArchive`  
  
## Anforderungen  
 **Header:**  afx.h  
  
## Siehe auch  
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)   
 [CFile Class](../../mfc/reference/cfile-class.md)   
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [CSocket Class](../../mfc/reference/csocket-class.md)   
 [CSocketFile Class](../../mfc/reference/csocketfile-class.md)