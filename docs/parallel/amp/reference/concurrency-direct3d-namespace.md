---
title: "Concurrency::direct3d-Namespace"
ms.custom: na
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: na
ms.suite: na
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: na
ms.topic: "article"
f1_keywords: 
  - "amp/Concurrency::direct3d"
  - "amprt/Concurrency::direct3d"
  - "amp_short_vectors/Concurrency::direct3d"
  - "amp_graphics/Concurrency::direct3d"
  - "amp_math/Concurrency::direct3d"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "direct3d-Namespace"
ms.assetid: 9566a2f1-4d5f-43e4-a3ac-676643d38420
caps.latest.revision: 15
caps.handback.revision: "10"
ms.author: "mblome"
manager: "ghogen"
---
# Concurrency::direct3d-Namespace
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Der `direct3d`\-Namespace enthält Funktionen, welche die D3D\-Interoperabilität unterstützen.  Dies ermöglicht die einfache Verwendung von D3D\-Ressourcen zur Berechnung von AMP\-Code sowie die Verwendung von in AMP erstellen Ressourcen in D3D\-Code, ohne dass redundante Zwischenkopien erstellt werden.  Sie können die berechnungsintensiven Abschnitte der Ihrer DirectX\-Anwendungen inkrementell beschleunigen, indem Sie C\+\+ AMP verwenden und die D3D\-API für Daten nutzen, die aus AMP\-Berechnungen resultieren.  
  
## Syntax  
  
```  
namespace direct3d;  
```  
  
## Member  
  
### Klassen  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[scoped\_d3d\_access\_lock\-Klasse](../../../parallel/amp/reference/scoped-d3d-access-lock-class.md)|Ein RAII\-Wrapper für eine D3D\-Zugriffssperre auf einem `accelerator_view`\-Objekt.|  
  
### Strukturen  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[adopt\_d3d\_access\_lock\_t\-Struktur](../../../parallel/amp/reference/adopt-d3d-access-lock-t-structure.md)|Der Tagtyp, mit dem angegeben wird, dass die D3D\-Zugriffssperre eher übernommen als abgerufen werden sollte.|  
  
### Funktionen  
  
|Name|**Beschreibung**|  
|----------|----------------------|  
|[abs\-Funktion](../Topic/abs%20Function.md)|Gibt den absoluten Wert des Arguments zurück.|  
|[clamp\-Funktion](../Topic/clamp%20Function.md)|Überladen.  Bindet \_X an den angegebenen \_Min\- und \_Max\-Bereich|  
|[countbits\-Funktion](../Topic/countbits%20Function.md)|Zählt die Anzahl der festgelegten Bits in \_X|  
|[create\_accelerator\_view\-Funktion](../Topic/create_accelerator_view%20Function.md)|Erstellt eine [accelerator\_view\-Klasse](../../../parallel/amp/reference/accelerator-view-class.md) von einem Zeiger auf die Schnittstelle eines Direct3D\-Geräts|  
|[d3d\_access\_lock\-Funktion](../Topic/d3d_access_lock%20Function.md)|Ruft eine Sperre für eine accelerator\_view ab, um D3D\-Vorgänge in Ressourcen, die gemeinsam mit der accelerator\_view genutzt werden, sicher ausführen zu können.|  
|[d3d\_access\_try\_lock\-Funktion](../Topic/d3d_access_try_lock%20Function.md)|Versuch, ohne Blockierung die D3D\-Zugriffssperre für eine accelerator\_view abzurufen.|  
|[d3d\_access\_unlock\-Funktion](../Topic/d3d_access_unlock%20Function.md)|Gibt die D3D\-Zugriffssperre für die angegebene accelerator\_view frei.|  
|[firstbithigh\-Funktion](../Topic/firstbithigh%20Function.md)|Ruft den Speicherort des ersten festgelegten Bits in \_X ab und arbeitet dabei vom höchsten Bit in der Reihenfolge nach unten.|  
|[firstbitlow\-Funktion](../Topic/firstbitlow%20Function.md)|Ruft den Speicherort des ersten festgelegten Bits in \_X ab und arbeitet dabei vom niedrigsten Bit in der Reihenfolge nach oben.|  
|[get\_buffer\-Funktion](../Topic/get_buffer%20Function.md)|Ruft die Schnittstelle des D3D\-Puffers ab, die einem Array zugrunde liegt.|  
|[imax\-Funktion](../Topic/imax%20Function.md)|Vergleicht zwei Werte und gibt den größeren Wert zurück.|  
|[imin\-Funktion](../Topic/imin%20Function.md)|Vergleicht zwei Werte und gibt den kleineren Wert zurück.|  
|[is\_timeout\_disabled\-Funktion](../Topic/is_timeout_disabled%20Function.md)|Gibt ein boolesches Flag zurück, das angibt, ob Timeout für die angegebene "accelerator\_view" deaktiviert ist.|  
|[mad\-Funktion](../Topic/mad%20Function.md)|Überladen.  Führt ein arithmetische Multiplikations\-Additions\-Operation für drei Argumenten aus: \_X \* \_Y \+ \_Z|  
|[make\_array\-Funktion](../Topic/make_array%20Function.md)|Erstellt ein Array aus dem Schnittstellenzeiger eines D3D\-Puffers.|  
|[noise\-Funktion](../Topic/noise%20Function.md)|Generiert mithilfe des Perlin\-Noise\-Algorithmus einen Zufallswert|  
|[Bogenmaßfunktion](../Topic/radians%20Function.md)|Konvertiert \_X von Grad in Bogenmaß|  
|[rcp\-Funktion](../Topic/rcp%20Function.md)|Berechnet einen schnellen, ungefähren Kehrwert des Arguments|  
|[reversebits\-Funktion](../Topic/reversebits%20Function.md)|Kehrt die Reihenfolge der Bits in \_X um|  
|[Sättigungsfunktion](../Topic/saturate%20Function.md)|Bindet \_X im Bereich zwischen 0 und 1|  
|[sign\-Funktion](../Topic/sign%20Function.md)|Überladen.  Gibt das Vorzeichen des Arguments zurück|  
|[smoothstep\-Funktion](../Topic/smoothstep%20Function.md)|Gibt eine glatte Hermite\-Interpolation zwischen 0 und 1 zurück, wenn \_X im Bereich \[\_Min, \_Max\] liegt.|  
|[Schrittfunktion](../Topic/step%20Function.md)|Vergleicht zwei Werte und gibt, je nachdem welcher Wert größer ist, 0 oder 1 zurück|  
|[umax\-Funktion](../Topic/umax%20Function.md)|Vergleicht zwei unsignierte Werte und gibt den größeren Wert zurück.|  
|[umin\-Funktion](../Topic/umin%20Function.md)|Vergleicht zwei unsignierte Werte und gibt den kleineren Wert zurück.|  
  
## Anforderungen  
 **Header:** amp.h  
  
 **Namespace:** Nebenläufigkeit  
  
## Siehe auch  
 [Concurrency\-Namespace \(C\+\+ AMP\)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)