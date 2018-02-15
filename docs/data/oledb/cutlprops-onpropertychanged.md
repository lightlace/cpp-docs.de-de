---
title: 'CUtlProps:: OnPropertyChanged | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- OnPropertyChanged
- CUtlProps.OnPropertyChanged
- CUtlProps::OnPropertyChanged
dev_langs:
- C++
helpviewer_keywords:
- OnPropertyChanged method
ms.assetid: c5924210-b685-46c4-87f8-1b81e5bd3378
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 3117a22a2b08b95528692d88cfb6e136d209e346
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/14/2018
---
# <a name="cutlpropsonpropertychanged"></a>CUtlProps::OnPropertyChanged
Wird aufgerufen, nach dem Festlegen einer Eigenschaft für die verkettete Eigenschaften zu behandeln.  
  
## <a name="syntax"></a>Syntax  
  
```cpp
      virtual HRESULT OnPropertyChanged(ULONG /* iCurSet */,  
   DBPROP* pDBProp);  
```  
  
#### <a name="parameters"></a>Parameter  
 `iCurSet`  
 Der Index im Array Eigenschaftensatz; 0 (null), wenn nur eine Eigenschaft festgelegt ist.  
  
 `pDBProp`  
 Die Eigenschafts-ID und den neuen Wert in einem [DBPROP](https://msdn.microsoft.com/en-us/library/ms717970.aspx) Struktur.  
  
## <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT`-Objekt. Der Standardrückgabewert ist `S_OK`.  
  
## <a name="remarks"></a>Hinweise  
 Wenn verkettete Eigenschaften, z. B. Lesezeichen oder Updates, deren Werte den Wert einer anderen Eigenschaft abhängig sind, verarbeiten soll, sollten Sie diese Funktion überschreiben.  
  
## <a name="example"></a>Beispiel  
 In dieser Funktion der Benutzer erhält die Eigenschafts-ID aus der `DBPROP*` Parameter. Nun ist es möglich, vergleichen Sie die ID für eine Eigenschaft zu verketten. Wenn die Eigenschaft gefunden wird, `SetProperties` wird aufgerufen, mit der Eigenschaft, die jetzt in Verbindung mit der anderen Eigenschaft festgelegt werden. In diesem Fall, wenn eine erhält die `DBPROP_IRowsetLocate`, `DBPROP_LITERALBOOKMARKS`, oder `DBPROP_ORDEREDBOOKMARKS` Eigenschaft, die eine Festlegen der `DBPROP_BOOKMARKS` Eigenschaft.  
  
 [!code-cpp[NVC_OLEDB_Provider#2](../../data/oledb/codesnippet/cpp/cutlprops-onpropertychanged_1.h)]  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** „atldb.h“  
  
## <a name="see-also"></a>Siehe auch  
 [CUtlProps-Klasse](../../data/oledb/cutlprops-class.md)