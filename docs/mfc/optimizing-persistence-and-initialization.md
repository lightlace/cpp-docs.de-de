---
title: "Optimieren von Persistenz und Initialisierung"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MFC-ActiveX-Steuerelemente, Optimieren"
  - "Optimierung, ActiveX-Steuerelemente"
  - "Optimieren der Leistung, ActiveX-Steuerelemente"
  - "Leistung, ActiveX-Steuerelemente"
ms.assetid: e821e19e-b9eb-49ab-b719-0743420ba80b
caps.latest.revision: 10
caps.handback.revision: "6"
ms.author: "mblome"
manager: "ghogen"
---
# Optimieren von Persistenz und Initialisierung
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Standardmäßig werden und Dauerhaftigkeit Initialisierung in einem Steuerelement durch die `DoPropExchange`\-Memberfunktion.  In einem typischen Steuerelement enthält diese Funktion werden Aufrufe an einige **PX\_**\-Funktionen \(`PX_Color`, `PX_Font`, z.\), einen für jede Eigenschaft.  
  
 Dieser Ansatz hat den Vorteil, dass eine einzelne `DoPropExchange` Implementierung zur Initialisierung, zur Beibehaltung im Binärformat und zur Beibehaltung im so genannten "Eigenschaftensammlungs" Format verwendet werden kann, das durch mehrere Container verwendet wird.  Diese eine Funktion bietet alle Informationen über die Eigenschaften und deren Standardwerte in einem geeigneten Ort.  
  
 Allerdings enthält dieses Allgemeine auf Kosten von Effizienz.  Die **PX\_**\-Funktionen rufen ihre Flexibilität von mehrschichtige Implementierungen, die naturgemäß weniger effizient als mehr direkt sind, das weniger flexible, Ansätze ab.  Wenn ein Steuerelement einen Standardwert zu **PX\_** eine Funktion übergeben wird, muss dieser Standardwert, sogar in Situationen jedes Mal bereitgestellt werden, wenn der Standardwert möglicherweise nicht notwendigerweise verwendet wird.  Wenn, den Standardwert zu generieren eine nicht\-triviale Aufgabe wird \(beispielsweise, wenn der Wert einer Ambient\-Eigenschaft abgerufen wurde\), dann sind zusätzliche, unnötige Arbeit ausgeführt, wenn der Standardwert nicht verwendet wird.  
  
 Sie können Persistenzleistung des Steuerelements verbessern binäre, indem Sie `Serialize`\-Funktion des Steuerelements überschreiben.  Die Standardimplementierung dieser Memberfunktion macht einen Aufruf der Funktion `DoPropExchange`.  Durch sie überschreiben, können Sie eine direktere Implementierung für die Beibehaltung bereitstellen.  Angenommen diese `DoPropExchange`\-Funktion:  
  
 [!CODE [NVC_MFC_AxOpt#1](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxOpt#1)]  
  
 Um die Leistung der binären Dauerhaftigkeit dieses Steuerelements zu verbessern, können Sie die `Serialize`\-Funktion überschreiben wie folgt:  
  
 [!CODE [NVC_MFC_AxOpt#2](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxOpt#2)]  
  
 Die lokale Variable `dwVersion` kann verwendet werden, um die Version des dauerhaften Zustands geladen oder gespeicherten des Steuerelements zu erkennen.  Sie können diese Variable verwenden, anstatt, [CPropExchange::GetVersion](../Topic/CPropExchange::GetVersion.md) aufzurufen.  
  
 Um ein wenig Platz im persistenten Format für eine **BOOL**\-Eigenschaft zu speichern \(und halten diese kompatibel mit dem Format erzeugt durch `PX_Bool`\), können Sie die Eigenschaft als **BYTE** speichern, wie folgt:  
  
 [!CODE [NVC_MFC_AxOpt#3](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxOpt#3)]  
  
 Wie Sie im Lastfall, eine temporäre Variable wird verwendet und anschließend der Wert zugewiesen, anstatt, Downcasting `m_boolProp` zu einem Verweis **BYTE**.  Das Gussverfahren würde nur ein Byte von `m_boolProp` zu, das geändert wurde und fehlgeschlagen würde die übrigen Bytes nicht initialisiert.  
  
 Für das gleiche Steuerelement können Sie die Initialisierung des Steuerelements optimieren, indem Sie [COleControl::OnResetState](../Topic/COleControl::OnResetState.md) überschreiben, wie folgt:  
  
 [!CODE [NVC_MFC_AxOpt#4](../CodeSnippet/VS_Snippets_Cpp/NVC_MFC_AxOpt#4)]  
  
 Obwohl `Serialize` und `OnResetState` überschrieben wurden, sollte die Funktion `DoPropExchange` unverändert beibehalten werden, da sie weiterhin zur Beibehaltung im Eigenschaftensammlungsformat verwendet wird.  Es ist wichtig, alle diese drei Funktionen zu, um sicherzustellen, dass das Steuerelement die Eigenschaften konsistent verwaltet, unabhängig von der Persistenzmechanismus der Container verwendet.  
  
## Siehe auch  
 [MFC\-ActiveX\-Steuerelemente: Optimierung](../mfc/mfc-activex-controls-optimization.md)