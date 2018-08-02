---
title: AsWeak-Funktion | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::AsWeak
dev_langs:
- C++
helpviewer_keywords:
- AsWeak function
ms.assetid: a6f10cfc-c1d6-4761-adb9-1a119cc99913
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: a51b7095ec654c4ebb393c9a83d1e30fb52ce019
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/02/2018
ms.locfileid: "39462624"
---
# <a name="asweak-function"></a>AsWeak-Funktion
Ruft einen schwachen Verweis zur angegebenen Instanz ab.  
  
## <a name="syntax"></a>Syntax  
  
```  
template<typename T>  
HRESULT AsWeak(  
   _In_ T* p,  
   _Out_ WeakRef* pWeak  
);  
```  
  
#### <a name="parameters"></a>Parameter  
 *T*  
 Ein Zeiger auf den Typ des Parameters *p*.  
  
 *p*  
 Eine Instanz eines Typs.  
  
 *pWeak*  
 Wenn dieser Vorgang abgeschlossen ist, einen Zeiger auf einen schwachen Verweis auf Parameter *p*.  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn dieser Vorgang erfolgreich ist; andernfalls ein Fehler HRESULT, das die Ursache des Fehlers angibt.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** client.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [Microsoft::WRL-Namespace](../windows/microsoft-wrl-namespace.md)