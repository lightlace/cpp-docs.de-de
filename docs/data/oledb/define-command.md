---
title: DEFINE_COMMAND | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- DEFINE_COMMAND
dev_langs:
- C++
helpviewer_keywords:
- DEFINE_COMMAND macro
ms.assetid: 9d724968-e242-413c-9a13-e7175fccf9b1
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f95fafbd9a63c5bf31add8bad1a8757bdcb60ae1
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="definecommand"></a>DEFINE_COMMAND
Gibt den Befehl an, der verwendet wird, um das Rowset zu erstellen, bei Verwendung der [CCommand](../../data/oledb/ccommand-class.md) Klasse. Akzeptiert nur Zeichenfolgen-Datentypen, die den angegebenen Anwendungstyp (ANSI oder Unicode) entsprechen.  
  
> [!NOTE]
>  Es wird empfohlen, die Verwendung von [DEFINE_COMMAND_EX](../../data/oledb/define-command-ex.md) anstelle von `DEFINE_COMMAND`.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
DEFINE_COMMAND(x, szCommand)  
  
```  
  
#### <a name="parameters"></a>Parameter  
 *w*  
 [in] Der Name der Benutzerdatensatzklasse (Befehl).  
  
 `szCommand`  
 [in] Der Befehlszeichenfolge, die verwendet wird, um das Rowset zu erstellen, bei Verwendung [CCommand](../../data/oledb/ccommand-class.md).  
  
## <a name="remarks"></a>Hinweise  
 Die Befehlszeichenfolge, die Sie angeben, wird als Standard verwendet werden, wenn Sie keinen Befehlstext im Angeben der [CCommand:: Open](../../data/oledb/ccommand-open.md) Methode.  
  
 Dieses Makro akzeptiert ANSI-Zeichenfolgen, wenn es sich bei Erstellen der Anwendung als ANSI oder Unicode-Zeichenfolgen, wenn Sie eine Anwendung im Unicode-Format erstellen. Es wird empfohlen, die Verwendung von [DEFINE_COMMAND_EX](../../data/oledb/define-command-ex.md) anstelle von `DEFINE_COMMAND`, da der erste Wert akzeptiert, die Unicode-Zeichenfolgen, unabhängig von den Anwendungstyp ANSI oder Unicode.  
  
## <a name="example"></a>Beispiel  
 Finden Sie unter [BOOKMARK_ENTRY](../../data/oledb/bookmark-entry.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [Makros und globale Funktionen für OLE-Consumervorlagen](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)