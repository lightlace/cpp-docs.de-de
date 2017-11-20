---
title: DEFINE_COMMAND_EX | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: DEFINE_COMMAND_EX
dev_langs: C++
helpviewer_keywords: DEFINE_COMMAND_EX macro
ms.assetid: d3e2ef20-1455-46d2-8499-8ab84bbb90a4
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 9b3386f420e3af97ab01defbe57303a8100a2965
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="definecommandex"></a>DEFINE_COMMAND_EX
Gibt den Befehl an, der verwendet wird, um das Rowset zu erstellen, bei Verwendung der [CCommand](../../data/oledb/ccommand-class.md) Klasse. Unterstützt Unicode und ANSI-Anwendungen.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
DEFINE_COMMAND_EX(  
x  
,   
wszCommand  
 )  
  
```  
  
#### <a name="parameters"></a>Parameter  
 *x*  
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