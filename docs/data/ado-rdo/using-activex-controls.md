---
title: "Verwenden von ActiveX-Steuerelementen | Microsoft Docs"
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
  - "ActiveX-Steuerelemente [C++], Informationen über ActiveX-Steuerelemente"
  - "Steuerelemente [C++], ActiveX"
ms.assetid: 33442173-205d-492f-82c8-9a8105358ec6
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Verwenden von ActiveX-Steuerelementen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Die Themen in diesem Abschnitt bieten eine Übersicht zur Verwendung von ActiveX\-Steuerelementen.  
  
 Bei einem ActiveX\-Steuerelement handelt es sich um eine COM\-Komponente, die Standardschnittstellen im Hinblick auf Dauerhaftigkeit, Verbindungspunkte und Hosting unterstützt.  Durch diese Standardschnittstellen wird ein Protokoll definiert, das festlegt, wie ein Steuerelement in einem Steuerelementcontainer gehostet wird, wie es Meldungen austauscht und Ereignisse verarbeitet.  
  
 ActiveX\-Steuerelemente in Form von COM\-Servern verfügen über folgende Komponenten:  
  
|Begriff|**Beschreibung**|  
|-------------|----------------------|  
|Eigenschaften|Steuerelemente verfügen über Membervariablen zur Darstellung des internen Zustands und werden als **Get**\- und `Set`\-Accessorfunktionen implementiert.  Eine **Get**\-Funktion wird für jede Accessormethode mit einem propget\-Tag in der IDL\-Datei generiert.  Eine `Set`\-Funktion wird für jede Accessormethode mit einem propput\- oder propputref\-IDL\-Tag generiert.<br /><br /> Mithilfe von [Wrapperklassen](../../data/ado-rdo/wrapper-classes.md) oder des [OLE\/COM\-Objektkatalogs](../../data/ado-rdo/using-the-ole-com-object-viewer.md) können Sie ermitteln, wie Accessorfunktionen definiert werden.|  
|Methoden|Das Verhalten eines Steuerelements wird durch seine öffentlichen Methoden definiert.  Wrapperklassen bieten Zugriff auf die Methoden eines Steuerelements.<br /><br /> Wenn Sie keine Wrapperklassen verwenden \(Standard\), können Sie über einen Schnittstellenzeiger auf die Methoden eines Steuerelements zugreifen.<br /><br /> Ein Beispiel für eine öffentliche Methode ist die **Refresh**\-Methode im ADO\-Datensteuerelement, mit der das abgerufene Rowset aktualisiert wird.|  
|Ereignisse|Ein Steuerelement kann ein Ereignis generieren, um den Host über einen Vorgang zu benachrichtigen.  Ein Beispiel dafür ist das `OnClick`\-Ereignis des Schaltflächensteuerelements.  Sobald auf die Schaltfläche geklickt wird, generiert diese ein `OnClick`\-Ereignis.  Verfügt der Host des Steuerelements über einen Handler für dieses Ereignis, wird dieser ausgeführt.|  
|Typbibliothek|Eine Typbibliothek informiert einen Steuerelementcontainer über die Eigenschaften, Methoden und Ereignisse, die von einem Steuerelement unterstützt werden.  Typbibliotheken werden entweder als separate Dateien \(mit einer TLB\-Erweiterung\) oder innerhalb des Steuerelements verwendet.<br /><br /> Sie enthalten außerdem Informationen zu den Co\-Klassen des Steuerelements.  Bei einer Co\-Klasse handelt es sich um eine COM\-Klasse, die mit einer GUID gekennzeichnet ist.  Eine Co\-Klasse umfasst eine oder mehrere Schnittstellen, die vom Steuerelement definiert werden.<br /><br /> Um Typbibliotheken zu überprüfen, verwenden Sie den [OLE\/COM\-Objektkatalog](../../data/ado-rdo/using-the-ole-com-object-viewer.md).|  
  
 In den folgenden Themen wird die Verwendung eines ActiveX\-Steuerelements beschrieben:  
  
-   [Einfügen des Steuerelements in eine Visual C\+\+\-Anwendung](../../data/ado-rdo/inserting-the-control-into-a-visual-cpp-application.md)  
  
-   [Wrapperklassen](../../data/ado-rdo/wrapper-classes.md)  
  
-   [Erstellen von Datenbankverbindungen](../../data/ado-rdo/creating-database-connections.md)  
  
-   [Festlegen von Steuerelementeigenschaften zur Entwurfszeit](../../data/ado-rdo/setting-control-properties-at-design-time.md)  
  
-   [Festlegen von Ereignishandlern für ActiveX\-Steuerelemente](../../data/ado-rdo/setting-event-handlers-on-activex-controls.md)  
  
-   [Ändern des Laufzeitverhaltens eines Steuerelements](../../data/ado-rdo/modifying-a-control-s-run-time-behavior.md)  
  
-   [Weiterverteilen von Steuerelementen](../../data/ado-rdo/redistributing-controls.md)  
  
## Siehe auch  
 [Datengebundene Steuerelemente \(ADO und RDO\)](../../data/ado-rdo/data-bound-controls-ado-and-rdo.md)