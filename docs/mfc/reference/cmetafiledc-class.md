---
title: "CMetaFileDC Class"
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
  - "CMetaFileDC"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMetaFileDC class"
  - "Metadateien, Implementieren"
  - "Windows metafiles [C++]"
ms.assetid: ffce60fa-4181-4d46-9832-25e46fad4db4
caps.latest.revision: 23
caps.handback.revision: "9"
ms.author: "mblome"
manager: "ghogen"
---
# CMetaFileDC Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Implementiert eine Windows\-Metadatei, die eine Sequenz von GDI \(Graphics Device Interface\) \- Befehlen enthält, dass Sie wiedergeben können, um ein gewünschtes Bild zu erstellen oder zu Text.  
  
## Syntax  
  
```  
class CMetaFileDC : public CDC  
```  
  
## Mitglieder  
  
### Öffentliche Konstruktoren  
  
|Name|Description|  
|----------|-----------------|  
|[CMetaFileDC::CMetaFileDC](../Topic/CMetaFileDC::CMetaFileDC.md)|Erstellt ein `CMetaFileDC`\-Objekt.|  
  
### Öffentliche Methoden  
  
|Name|Description|  
|----------|-----------------|  
|[CMetaFileDC::Close](../Topic/CMetaFileDC::Close.md)|Schließt den Gerätekontext und stellt ein Metadateihandle erstellt.|  
|[CMetaFileDC::CloseEnhanced](../Topic/CMetaFileDC::CloseEnhanced.md)|Schließt einen Gerätekontext der erweiterten Metadatei und stellt ein Handle der erweiterten Metadatei erstellt.|  
|[CMetaFileDC::Create](../Topic/CMetaFileDC::Create.md)|Erstellt den Windows\-Metadateigerätekontext und fügt ihn dem `CMetaFileDC`\-Objekt.|  
|[CMetaFileDC::CreateEnhanced](../Topic/CMetaFileDC::CreateEnhanced.md)|Erstellt einen Metadateigerätekontext für eine ErhöhenFormat Metadatei.|  
  
## Hinweise  
 Um eine Windows\-Metadatei zu implementieren, erstellen Sie zuerst ein `CMetaFileDC`\-Objekt.  Rufen Sie den `CMetaFileDC`\-Konstruktor auf, und rufen Sie dann die [Erstellen Sie](../Topic/CMetaFileDC::Create.md)\-Memberfunktion auf, die einen Windows\-Metadateigerätekontext erstellt und es in `CMetaFileDC`\-Objekt angefügt werden.  
  
 Senden Sie als Nächstes das `CMetaFileDC`\-Objekt, das die Sequenz von `CDC` GDI Befehle, die für sie bestimmen wiederzugeben.  Nur die GDI\-Befehle, die Ausgabe, wie `MoveTo` und `LineTo` erstellen, können verwendet werden.  
  
 Nachdem Sie die gewünschten Befehle zur Metadatei gesendet haben, rufen Sie die **Schließen**\-Memberfunktion auf, die die Metadateigerätekontexte schließt und ein Metadateihandle zurückgibt.  Löschen Sie dann das `CMetaFileDC`\-Objekt.  
  
 [CDC::PlayMetaFile](../Topic/CDC::PlayMetaFile.md) kann das Metadateihandle dann verwenden, um die Metadatei wiederholt abgespielt.  Die Metadatei kann von Windows\-Funktionen wie [CopyMetaFile](http://msdn.microsoft.com/library/windows/desktop/dd183480) auch bearbeitet werden, die eine Metadatei auf dem Datenträger kopiert.  
  
 Wenn die Metadatei nicht mehr benötigt wird, löschen Sie sie aus dem Arbeitsspeicher mit der [DeleteMetaFile](http://msdn.microsoft.com/library/windows/desktop/dd183537) Windows\-Funktion.  
  
 Sie können das `CMetaFileDC`\-Objekt auch implementieren, damit es ausgegebene Aufrufe behandeln und GDI\-Aufrufe wie `GetTextExtent` finden kann.  Eine solche Metadatei ist flexibler und kann allgemeinen GDI\-Code einfach wiederverwenden, der häufig aus einer Kombination der Ausgabe besteht und Attribut aufruft.  Die `CMetaFileDC`\-Klasse erbt zwei Gerätekontexte, `m_hDC` und `m_hAttribDC`, von `CDC`.  Der `m_hDC` Gerätekontext behandelt alle Ausgabeaufrufe [CDC](../../mfc/reference/cdc-class.md) GDI und die `m_hAttribDC` Gerätekontexthandles alle Attributaufrufe `CDC` GDI.  Normalerweise auf diese zwei Gerätekontexte dasselbe Gerät an.  Bei `CMetaFileDC` wird das Attribut DC zu **NULL** standardmäßig festgelegt.  
  
 Erstellen Sie einen zweiten Gerätekontext, der auf den Bildschirm, einen Drucker oder das Gerät unterschiedlich eine Metadatei zeigt, und rufen Sie dann die `SetAttribDC`\-Memberfunktion auf, um den neuen Gerätekontext mit `m_hAttribDC` zuzuordnen.  GDI\-Aufrufe für Informationen werden nun auf neue `m_hAttribDC` verwiesen.  Aufrufe der Ausgabe GDI wechseln zu `m_hDC`, das die Metadatei darstellt.  
  
 Weitere Informationen zu `CMetaFileDC`, finden Sie unter [Gerätekontexte](../../mfc/device-contexts.md).  
  
## Vererbungshierarchie  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CDC](../../mfc/reference/cdc-class.md)  
  
 `CMetaFileDC`  
  
## Anforderungen  
 **Header:**  afxext.h  
  
## Siehe auch  
 [CDC\-Klasse](../../mfc/reference/cdc-class.md)   
 [Hierarchiediagramm](../../mfc/hierarchy-chart.md)