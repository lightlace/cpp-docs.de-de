---
title: 'Ftmbase:: GetUnmarshalClass-Methode | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- ftm/Microsoft::WRL::FtmBase::GetUnmarshalClass
dev_langs:
- C++
helpviewer_keywords:
- GetUnmarshalClass method
ms.assetid: 535fc539-5b97-4967-b158-f7568f13d341
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 09afd9f977dbc779eb1dc10e9553d2ca88538fcc
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/08/2018
---
# <a name="ftmbasegetunmarshalclass-method"></a>FtmBase::GetUnmarshalClass-Methode
Ruft die CLSID, die COM verwendet, um die DLL, die den Code für den entsprechenden Proxy zu suchen. COM lädt diese DLL aus, um eine nicht initialisierte Instanz des Proxys zu erstellen.  
  
## <a name="syntax"></a>Syntax  
  
```  
STDMETHODIMP GetUnmarshalClass(  
   __in REFIID riid,  
   __in_opt void *pv,  
   __in DWORD dwDestContext,  
   __reserved void *pvDestContext,  
   __in DWORD mshlflags,  
   __out CLSID *pCid  
) override;  
```  
  
#### <a name="parameters"></a>Parameter  
 `riid`  
 Verweis auf den Bezeichner der Schnittstelle, die gemarshallt werden.  
  
 `pv`  
 Zeiger auf die Schnittstelle, die gemarshallt werden; NULL kann sein, wenn der Aufrufer nicht über einen Zeiger auf die gewünschte Schnittstelle besitzt.  
  
 `dwDestContext`  
 Zielkontext, in dem die angegebene Schnittstelle werden rückgängig gemacht werden.  
  
 Geben Sie eine oder mehrere MSHCTX-Enumerationswerte.  
  
 Methodeninformationen kann entweder in einem anderen Apartment des aktuellen Prozesses (MSHCTX_INPROC) oder in einem anderen Prozess auf dem gleichen Computer wie der aktuelle Prozess (MSHCTX_LOCAL) auftreten.  
  
 `pvDestContext`  
 Für die zukünftige Verwendung reserviert. NULL muss sein.  
  
 `mshlflags`  
 Wenn dieser Vorgang abgeschlossen wird, Zeiger auf die CLSID zum Erstellen eines Proxys im Clientprozess verwendet werden.  
  
 `pCid`  
  
## <a name="return-value"></a>Rückgabewert  
 S_OK, wenn erfolgreich; Anderenfalls "S_FALSE".  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** ftm.h  
  
 **Namespace:** Microsoft::WRL  
  
## <a name="see-also"></a>Siehe auch  
 [FtmBase-Klasse](../windows/ftmbase-class.md)