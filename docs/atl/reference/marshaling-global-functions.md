---
title: Marshalling von globalen Funktionen | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- atlbase/ATL::AtlFreeMarshalStream
- atlbase/ATL::AtlMarshalPtrInProc
- atlbase/ATL::AtlUnmarshalPtr
dev_langs: C++
ms.assetid: 877100b5-6ad9-44c5-a2e0-09414f1720d0
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 9692e326dc8256c29373b72181517925d729da87
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2017
---
# <a name="marshaling-global-functions"></a>Marshalling globale Funktionen
Diese Funktionen unterstützen Marshalling und Marshallen von Daten in Schnittstellenzeiger zu konvertieren.  
  
> [!IMPORTANT]
>  In der folgenden Tabelle aufgeführten Funktionen können nicht in Anwendungen verwendet werden, die in der Windows-Runtime ausgeführt werden.  
  
|||  
|-|-|  
|[AtlFreeMarshalStream](#atlfreemarshalstream)|Gibt die marschalldaten und die `IStream` Zeiger.|  
|[AtlMarshalPtrInProc](#atlmarshalptrinproc)|Erstellt ein neues Streamobjekt und marshallt den angegebenen Schnittstellenzeiger auf.|  
|[AtlUnmarshalPtr](#atlunmarshalptr)|Konvertiert einen Datenstrom Marshallen von Daten in einen Schnittstellenzeiger.|  

## <a name="requirements"></a>Anforderungen:
**Header:** atlbase.h
  
##  <a name="atlfreemarshalstream"></a>AtlFreeMarshalStream  
 Gibt die Marschalldaten im Stream und anschließend den Streamzeiger frei.  

```
HRESULT AtlFreeMarshalStream(IStream* pStream);
```  
  
### <a name="parameters"></a>Parameter  
 `pStream`  
 [in] Ein Zeiger auf die `IStream` Schnittstelle für den Stream für das Marshalling verwendet.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [AtlMarshalPtrInProc](#atlmarshalptrinproc).  
  
##  <a name="atlmarshalptrinproc"></a>AtlMarshalPtrInProc  
 Erstellt ein neues Streamobjekt, schreibt die CLSID des Proxys in den Stream und marshallt den angegebenen Schnittstellenzeiger durch Schreiben der für die Initialisierung des Proxys erforderlichen Daten in den Stream.  
  
```
HRESULT AtlMarshalPtrInProc(
    IUnknown* pUnk,
    const IID& iid,
    IStream** ppStream);
```  
  
### <a name="parameters"></a>Parameter  
 *pUnk*  
 [in] Ein Zeiger auf die Schnittstelle, die gemarshallt werden.  
  
 `iid`  
 [in] Die GUID der Schnittstelle, die gemarshallt werden.  
  
 `ppStream`  
 [out] Ein Zeiger auf die `IStream` Schnittstelle für das neue Streamobjekt, das für das Marshalling verwendet.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein standard HRESULT-Wert.  
  
### <a name="remarks"></a>Hinweise  
 Die **MSHLFLAGS_TABLESTRONG** Flag wird festgelegt, sodass der Zeiger in mehrere Streams gemarshallt werden kann. Der Zeiger kann auch Marshalling mehrmals sein.  
  
 Wenn ein Fehler auftritt, wird der streamzeiger freigegeben.  
  
 `AtlMarshalPtrInProc`kann nur auf einen Zeiger auf ein in-Process-Objekt verwendet werden.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_COM#50](../../atl/codesnippet/cpp/marshaling-global-functions_1.cpp)]  
  
##  <a name="atlunmarshalptr"></a>AtlUnmarshalPtr  
 Konvertiert die Marshallingdaten des Streams in einen Schnittstellenzeiger, der vom Client verwendet werden kann.  
   
```
HRESULT AtlUnmarshalPtr(
    IStream* pStream,
    const IID& iid,
    IUnknown** ppUnk);
```  
  
### <a name="parameters"></a>Parameter  
 `pStream`  
 [in] Ein Zeiger auf den Stream wird Marshalling.  
  
 `iid`  
 [in] Die GUID der Schnittstelle wird Marshalling.  
  
 `ppUnk`  
 [out] Ein Zeiger auf die Marshalling-Schnittstelle.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein standard HRESULT-Wert.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [AtlMarshalPtrInProc](#atlmarshalptrinproc).  
  
## <a name="see-also"></a>Siehe auch  
 [Funktionen](../../atl/reference/atl-functions.md)
