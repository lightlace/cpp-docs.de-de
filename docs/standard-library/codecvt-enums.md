---
title: '&lt;codecvt&gt;-Enumerationen | Microsoft-Dokumentation'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 46a8b073-01bc-46d3-b3d3-a8540f9422c1
caps.latest.revision: 10
manager: ghogen
translationtype: Machine Translation
ms.sourcegitcommit: 3168772cbb7e8127523bc2fc2da5cc9b4f59beb8
ms.openlocfilehash: 21162b7c25e09f2f77d2da1f4ee7797e68ec1e94
ms.lasthandoff: 02/24/2017

---
# <a name="ltcodecvtgt-enums"></a>&lt;codecvt&gt;-Enumerationen
  
##  <a name="a-namecodecvtmodeenumerationa--codecvtmode-enumeration"></a><a name="codecvt_mode_enumeration"></a> codecvt_mode-Enumeration  
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


