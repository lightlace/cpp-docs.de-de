---
title: DEFINE_COMMAND_EX | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- DEFINE_COMMAND_EX
dev_langs:
- C++
helpviewer_keywords:
- DEFINE_COMMAND_EX macro
ms.assetid: d3e2ef20-1455-46d2-8499-8ab84bbb90a4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b2a77fa0d6655edeee88df3c7c45e1936a766b40
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/04/2018
---
# <a name="definecommandex"></a>DEFINE_COMMAND_EX
Gibt den Befehl an, der verwendet wird, um das Rowset zu erstellen, bei Verwendung der [CCommand](../../data/oledb/ccommand-class.md) Klasse. Unterstützt Unicode und ANSI-Anwendungen.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
DEFINE_COMMAND_EX(x, wszCommand)  
  
```  
  
#### <a name="parameters"></a>Parameter  
 *w*  
 [in] Der Name der Benutzerdatensatzklasse (Befehl).  
  
 `wszCommand`  
 [in] Der Befehlszeichenfolge, die verwendet wird, um das Rowset zu erstellen, bei Verwendung [CCommand](../../data/oledb/ccommand-class.md).  
  
## <a name="remarks"></a>Hinweise  
 Die Befehlszeichenfolge, die Sie angeben, wird als Standard verwendet werden, wenn Sie keinen Befehlstext im Angeben der [CCommand:: Open](../../data/oledb/ccommand-open.md) Methode.  
  
 Dieses Makro akzeptiert Unicode-Zeichenfolgen, unabhängig von den Anwendungstyp. Dieses Makro wird bevorzugt über [DEFINE_COMMAND](../../data/oledb/define-command.md) da Unicode unterstützt und ANSI-Anwendungen.  
  
## <a name="example"></a>Beispiel  
 Finden Sie unter [BOOKMARK_ENTRY](../../data/oledb/bookmark-entry.md).  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [Makros und globale Funktionen für OLE-Consumervorlagen](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)