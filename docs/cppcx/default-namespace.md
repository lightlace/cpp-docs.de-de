---
title: "Standardnamespace | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "default_CPP"
dev_langs: 
  - "C++"
ms.assetid: 4712e9dc-57ba-43cc-811e-022e1dae4de8
caps.latest.revision: 6
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 6
---
# Standardnamespace
Der `default`\-Namespace umfasst die integrierten Typen, die von [!INCLUDE[cppwrt](../cppcx/includes/cppwrt-md.md)] \([!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)]\) unterstützt werden.  
  
## Syntax  
  
```  
namespace default;  
```  
  
## Mitglieder  
 Alle integrierte Typen erben die folgenden Member.  
  
|||  
|-|-|  
|[default::\(type\_name\)::Equals\-Methode](../cppcx/default-type-name-equals-method.md)|Bestimmt, ob das angegebene Objekt mit dem aktuellen Objekt identisch ist.|  
|[default::\(type\_name\)::GetHashCode\-Methode](../cppcx/default-type-name-gethashcode-method.md)|Gibt den Hashcode für diese Instanz zurück.|  
|[default::\(type\_name\)::GetType\-Methode](../cppcx/default-type-name-gettype-method.md)|Gibt eine Zeichenfolge zurück, die den aktuellen Typ darstellt.|  
|[default::\(type\_name\)::ToString\-Methode](../cppcx/default-type-name-tostring-method.md)|Gibt eine Zeichenfolge zurück, die den aktuellen Typ darstellt.|  
  
### Integrierte Typen  
  
|Name|Beschreibung|  
|----------|------------------|  
|`char16`|Ein nicht numerischer 16\-Bit\-Wert, der einen Unicode\-Codepunkt \(UTF\-16\) darstellt.|  
|`float32`|Eine 32\-Bit\-IEEE 754\-Gleitkommazahl.|  
|`float64`|Eine 64\-Bit\-IEEE 754\-Gleitkommazahl.|  
|`int16`|Eine 16\-Bit\-Ganzzahl mit Vorzeichen.|  
|`int32`|Eine 32\-Bit\-Ganzzahl mit Vorzeichen.|  
|`int64`|Eine 64\-Bit\-Ganzzahl mit Vorzeichen.|  
|`int8`|Eine numerischer 8\-Bit\-Wert mit Vorzeichen.|  
|`uint16`|Eine 16\-Bit\-Ganzzahl ohne Vorzeichen.|  
|`uint32`|Eine 32\-Bit\-Ganzzahl ohne Vorzeichen.|  
|`uint64`|Eine 64\-Bit\-Ganzzahl ohne Vorzeichen.|  
|`uint8`|Eine numerischer 8\-Bit\-Wert ohne Vorzeichen.|  
  
## Anforderungen  
 **Header:** vccorlib.h  
  
## Siehe auch  
 [Sprachreferenz zu Visual C\+\+](../cppcx/visual-c-language-reference-c-cx.md)