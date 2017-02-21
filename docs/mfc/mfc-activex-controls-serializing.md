---
title: "MFC-ActiveX-Steuerelemente: Serialisierung | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_wVerMinor"
  - "DoPropExchange"
  - "_wVerMajor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DoPropExchange-Methode"
  - "ExchangeVersion-Methode"
  - "GetVersion-Methode"
  - "MFC-ActiveX-Steuerelemente, Serialisieren"
  - "MFC-ActiveX-Steuerelemente, Versionsunterstützung"
  - "Versionsverwaltung von ActiveX-Steuerelementen"
  - "wVerMajor (globale Konstante)"
  - "wVerMinor (globale Konstante)"
ms.assetid: 9d57c290-dd8c-4853-b552-6f17f15ebedd
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# MFC-ActiveX-Steuerelemente: Serialisierung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dieser Artikel wird erläutert, wie ein ActiveX\-Steuerelement serialisiert.  Serialisierung ist der Prozess der Lesen und Schreiben von einem permanenten Speichermedium des Speichers, wie einer Datenträgerdatei.  Die MFC\-Bibliothek \(Microsoft Foundation \(MFC\) bietet integrierte Unterstützung für Serialisierung in der Klasse `CObject`.  `COleControl` erweitert diese Unterstützung von ActiveX\-Steuerelementen mithilfe eines Eigenschaftenaustauschmechanismus.  
  
 Serialisierung für ActiveX\-Steuerelemente wird implementiert, indem [COleControl::DoPropExchange](../Topic/COleControl::DoPropExchange.md).  Diese Funktion, aufgerufen beim Laden und Speichern der des Steuerelementobjekts, speichert alle Eigenschaften, die einer Membervariablen oder eine Membervariable mit Änderungsbenachrichtigung implementiert werden.  
  
 Die folgenden Themen enthalten die Kernfragen, die zum Serialisieren eines ActiveX\-Steuerelements verknüpft werden:  
  
-   `DoPropExchange` \-Funktion implementiert, um das Steuerelement zu serialisieren ein, befassen Sie  
  
-   [Anpassen des Serialisierungs\-Prozesses](#_core_customizing_the_default_behavior_of_dopropexchange)  
  
-   [Implementieren der Versions\-Unterstützung](#_core_implementing_version_support)  
  
##  <a name="_core_implementing_the_dopropexchange_function"></a> Implementieren der DoPropExchange\-Funktion  
 Wenn Sie den ActiveX\-Steuerelement\-Assistenten verwenden, um das Steuerelementprojekt zu generieren, werden mehrere Standardhandlerfunktionen automatisch der Steuerelementklasse, einschließlich die Standardimplementierung von [COleControl::DoPropExchange](../Topic/COleControl::DoPropExchange.md) hinzugefügt.  Das folgende Beispiel zeigt den Code, der auf Klassen hinzugefügt wird, die dem ActiveX\-Steuerelement\-Assistenten erstellt werden:  
  
 [!CODE [NVC_MFC_AxUI#43](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxUI#43)]  
  
 Wenn Sie eine Eigenschaft erhalten möchten, ändern Sie `DoPropExchange`, indem Sie einem Aufruf der Eigenschaftenaustauschfunktion hinzufügen.  Im folgenden Beispiel wird die benutzerdefinierte Serialisierung einer booleschen CircleShape\-Eigenschaft, in der die CircleShape\-Eigenschaft einen Standardwert verfügt: **TRUE**  
  
 [!CODE [NVC_MFC_AxSer#1](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxSer#1)]  
[!CODE [NVC_MFC_AxSer#2](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxSer#2)]  
  
 In der folgenden Tabelle werden die möglichen Eigenschaftenaustauschfunktionen auf, die Sie verwenden können, um die Steuerelementeigenschaften serialisiert:  
  
|Eigenschaftenaustauschfunktionen|Zweck|  
|--------------------------------------|-----------|  
|**PX\_Blob\(\)**|Serialisiert eine Typ Binary Large Object\-\(BLOB\)\- Dateneigenschaft.|  
|**PX\_Bool\(\)**|Serialisiert eine Eigenschaft vom Typ Booleschen Werts.|  
|**PX\_Color\(\)**|Serialisiert eine Typfarbeigenschaft.|  
|**PX\_Currency\(\)**|Serialisiert eine Eigenschaft **CY**\-Typ \(Währung\).|  
|**PX\_Double\(\)**|Serialisiert eine Typ **double**\-Eigenschaft.|  
|**PX\_Font\(\)**|Serialisiert eine Schriftarttypeneigenschaft.|  
|**PX\_Float\(\)**|Serialisiert eine Typ **float**\-Eigenschaft.|  
|**PX\_IUnknown\(\)**|Serialisiert eine Eigenschaft des Typs `LPUNKNOWN`.|  
|**PX\_Long\(\)**|Serialisiert eine Typ **long**\-Eigenschaft.|  
|**PX\_Picture\(\)**|Serialisiert eine Bildeigenschaft Typ.|  
|**PX\_Short\(\)**|Serialisiert eine Typ **short**\-Eigenschaft.|  
|**PX\_String\(\)**|Serialisiert Typ `CString` eine Eigenschaft.|  
|**PX\_ULong\(\)**|Serialisiert eine Typ **ULONG**\-Eigenschaft.|  
|**PX\_UShort\(\)**|Serialisiert eine Typ **USHORT**\-Eigenschaft.|  
  
 Weitere Informationen über diese Eigenschaftenaustauschfunktionen, finden Sie unter [Beibehaltung von OLE\-Steuerelementen](../mfc/reference/persistence-of-ole-controls.md) in der *MFC\-Referenz*.  
  
##  <a name="_core_customizing_the_default_behavior_of_dopropexchange"></a> Anpassen des Standardverhaltens von DoPropExchange  
 Die Standardimplementierung von **DoPropertyExchange** \(wie im vorherigen Thema gezeigt\) macht der Basisklasse ein Aufruf von `COleControl`.  Dies serialisiert den Satz von Eigenschaften, die automatisch vom `COleControl` unterstützt wird, der mehr Speicherplatz als nur verwendet, die benutzerdefinierten Eigenschaften des Steuerelements beim Serialisieren.  Das Entfernen dieses Aufrufs kann das Objekt, um nur Eigenschaften serialisiert, die Sie berücksichtigen wichtig.  Jede vordefinierte Eigenschaft gibt das Steuerelement hat implementiert wird nicht serialisiert an, wenn das Steuerelement welches Objekt Sie speichern oder laden, es sei denn, dass Sie explizit **PX\_** Aufrufe für sie hinzufügen.  
  
##  <a name="_core_implementing_version_support"></a> Implementieren der Versions\-Unterstützung  
 Versionsunterstützung kann ein überarbeitetes ActiveX\-Steuerelement, dauerhafte um neue Eigenschaften hinzuzufügen, und wurde noch in der Lage, die einen beständigen Zustand zu erkennen und zu laden, der mit einer früheren Version des Steuerelements erstellt wird.  Um die Version eines Steuerelements bereitzustellen als Teil seiner dauerhafter Daten, rufen Sie [COleControl::ExchangeVersion](../Topic/COleControl::ExchangeVersion.md) in der `DoPropExchange`\-Funktion des Steuerelements auf.  Dieser Aufruf wird automatisch eingefügt, wenn das ActiveX\-Steuerelement mithilfe des ActiveX\-Steuerelement\-Assistenten erstellt wurde.  Er kann entfernt werden, wenn Versionsunterstützung nicht benötigt.  Allerdings sind die Kosten in der der Steuerelementgröße \(4 Bytes\) für die eine höhere Flexibilität, die sehr klein Versionsunterstützung bereitstellt.  
  
 Wenn das Steuerelement nicht mit dem ActiveX\-Steuerelement\-Assistenten erstellt wurde, fügen Sie `COleControl::ExchangeVersion` einen Aufruf hinzu, indem Sie die folgende Zeile am Anfang der `DoPropExchange`\-Funktion einfügen \(vor dem Aufruf von `COleControl::DoPropExchange`\):  
  
 [!CODE [NVC_MFC_AxSer#1](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxSer#1)]  
[!CODE [NVC_MFC_AxSer#3](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxSer#3)]  
  
 Sie können ein beliebiges `DWORD` als Versionsnummer verwenden.  Projekten generiert durch die ActiveX\-Steuerelement\-Assistenten\-Verwendung **\_wVerMinor** und **\_wVerMajor** als Standard.  Diese sind globale Konstanten, die in der Implementierungsdatei der ActiveX\-Steuerelementklasse des Projekts definiert werden.  In den übrigen Teilen der Funktion `DoPropExchange`, können Sie jederzeit [CPropExchange::GetVersion](../Topic/CPropExchange::GetVersion.md) aufrufen, um die Version abzurufen, die Sie speichern oder abrufen.  
  
 Im folgenden Beispiel verfügt Version 1 dieses Beispielsteuerelements nur eine Eigenschaft "ReleaseDate".  Version 2 fügt eine Eigenschaft "OriginalDate" hinzu.  Wenn das Steuerelement angewiesen wird, den permanenten Zustand aus der alten Version zu laden, initialisiert es die Membervariable für die neue Eigenschaft auf einen Standardwert.  
  
 [!CODE [NVC_MFC_AxSer#4](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxSer#4)]  
[!CODE [NVC_MFC_AxSer#3](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxSer#3)]  
  
 Standardmäßig "konvertiert" ein Steuerelement alte Daten dem aktuellen Stil.  Wenn Version 2 eines Steuerelements Daten lädt, die bis Version 1 gespeichert wurden, wird das Format der Version 2, wenn wieder gespeichert wird.  Wenn Sie das Steuerelement speichern dauern soll, Daten im Format Lesen, führen **FALSE** als dritter Parameter, wenn sie `ExchangeVersion` aufrufen.  Im dritten Parameter ist optional und befindet **TRUE** standardmäßig.  
  
## Siehe auch  
 [MFC\-ActiveX\-Steuerelemente](../mfc/mfc-activex-controls.md)