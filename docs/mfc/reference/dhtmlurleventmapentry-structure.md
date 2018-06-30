---
title: DHtmlUrlEventMapEntry-Struktur | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- DHtmlUrlEventMapEntry
dev_langs:
- C++
helpviewer_keywords:
- DHtmlUrlEventMapEntry structure [MFC]
ms.assetid: 43117c1f-1a51-406c-aa2f-fea647080049
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ee629d9dcffc80ce20306989cad72d466722af87
ms.sourcegitcommit: 208d445fd7ea202de1d372d3f468e784e77bd666
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2018
ms.locfileid: "37123330"
---
# <a name="dhtmlurleventmapentry-structure"></a>DHtmlUrlEventMapEntry-Struktur
Die `DHtmlUrlEventMapEntry` Struktur bietet mehrere URL-Ereignis der Unterstützung von Karten.  
  
## <a name="syntax"></a>Syntax  
  
```  
struct DHtmlUrlEventMapEntry  
{  
LPCTSTR szUrl;  
const DHtmlEventMapEntry *pEventMap;  
};  
```  
  
#### <a name="parameters"></a>Parameter  
 *szUrl*  
 Die URL.  
  
 *pEventMap*  
 Die ereigniszuordnung mit der URL verknüpft ist.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** afxdhtml.h  
  
## <a name="see-also"></a>Siehe auch  
 [Strukturen, Stile, Rückrufe und Meldungszuordnungen](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)

