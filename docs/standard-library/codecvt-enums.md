---
title: '&lt;codecvt&gt;-Enumerationen | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- codecvt/std::codecvt_mode
ms.assetid: 46a8b073-01bc-46d3-b3d3-a8540f9422c1
helpviewer_keywords:
- std::codecvt_mode
caps.latest.revision: 
manager: ghogen
ms.openlocfilehash: 287f25eb023d00d8cff6ce39992affa39687f721
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/23/2018
---
# <a name="ltcodecvtgt-enums"></a>&lt;codecvt&gt;-Enumerationen
  
##  <a name="codecvt_mode"></a> codecvt_mode-Enumeration  
 Gibt Konfigurationsinformationen für [Gebietsschemafacets](../standard-library/locale-class.md) an.  
  
```  
enum codecvt_mode {  
    consume_header = 4,  
    generate_header = 2,  
    little_endian = 1  
 };  
```  
  
### <a name="remarks"></a>Hinweise  
 Die Enumeration definiert drei Konstanten, die Konfigurationsinformationen für Gebietsschemafacets angeben, die in [\<codecvt>](../standard-library/codecvt.md) deklariert sind. Die unterschiedlichen Werte lauten:  
  
- `consume_header`, um eine Sequenz des ursprünglichen Headers zu verwenden, wenn eine Multibytesequenz gelesen wird, und um die Bytereihenfolge der nachfolgenden zu lesenden Multibytesequenz zu bestimmen  
  
- `generate_header`, um eine Sequenz des ursprünglichen Headers zu generieren, wenn eine Multibytesequenz geschrieben wird, um die Bytereihenfolge der nachfolgenden zu schreibenden Multibytesequenz anzukündigen  
  
- `little_endian`, um eine Multibytesequenz in der Little-Endian-Reihenfolge zu generieren (und nicht in der standardmäßigen Big-Endian-Reihenfolge)  
  
 Diese Konstanten können mit OR beliebig kombiniert werden.  
  
## <a name="see-also"></a>Siehe auch  
 [\<codecvt>](../standard-library/codecvt.md)

