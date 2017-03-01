---
title: Marshallen von globalen Funktionen | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: 877100b5-6ad9-44c5-a2e0-09414f1720d0
caps.latest.revision: 19
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 5187996fc377bca8633360082d07f7ec8a68ee57
ms.openlocfilehash: dd4b8d50ec69974b7b2af29438b1657e1ce592b4
ms.lasthandoff: 02/24/2017

---
# <a name="marshaling-global-functions"></a>Marshalling globale Funktionen
Diese Funktionen unterstützen Marshalling und Marshallen von Daten in Schnittstellenzeiger umgewandelt.  
  
> [!IMPORTANT]
>  In der folgenden Tabelle aufgeführten Funktionen können nicht verwendet werden, in Anwendungen, die in Ausführen der [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  
  
|||  
|-|-|  
|[AtlFreeMarshalStream](#atlfreemarshalstream)|Gibt die marschalldaten und die `IStream` Zeiger.|  
|[AtlMarshalPtrInProc](#atlmarshalptrinproc)|Erstellt ein neues Streamobjekt und marshallt den angegebenen Schnittstellenzeiger.|  
|[AtlUnmarshalPtr](#atlunmarshalptr)|Konvertiert einen Datenstrom Marshallen von Daten in einen Schnittstellenzeiger.|  
  
##  <a name="a-nameatlfreemarshalstreama--atlfreemarshalstream"></a><a name="atlfreemarshalstream"></a>AtlFreeMarshalStream  
 Gibt die Marschalldaten im Stream und anschließend den Streamzeiger frei.  

```
HRESULT AtlFreeMarshalStream(IStream* pStream);
```  
  
### <a name="parameters"></a>Parameter  
 `pStream`  
 [in] Ein Zeiger auf die `IStream` Schnittstelle für den Stream für das Marshalling verwendet.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [AtlMarshalPtrInProc](#atlmarshalptrinproc).  
  
##  <a name="a-nameatlmarshalptrinproca--atlmarshalptrinproc"></a><a name="atlmarshalptrinproc"></a>AtlMarshalPtrInProc  
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
 Die **MSHLFLAGS_TABLESTRONG** Flag festgelegt ist, sodass der Zeiger in mehrere Datenströme gemarshallt werden kann. Der Zeiger kann auch Marshalling mehrmals sein.  
  
 Wenn Marshalling fehlschlägt, wird der streamzeiger freigegeben.  
  
 `AtlMarshalPtrInProc`kann nur auf einen Zeiger auf ein in-Process-Objekt verwendet werden.  
  
### <a name="example"></a>Beispiel  
 [!code-cpp[NVC_ATL_COM&#50;](../../atl/codesnippet/cpp/marshaling-global-functions_1.cpp)]  
  
##  <a name="a-nameatlunmarshalptra--atlunmarshalptr"></a><a name="atlunmarshalptr"></a>AtlUnmarshalPtr  
 Konvertiert die Marshallingdaten des Streams in einen Schnittstellenzeiger, der vom Client verwendet werden kann.  
   
```
HRESULT AtlUnmarshalPtr(
    IStream* pStream,
    const IID& iid,
    IUnknown** ppUnk);
```  
  
### <a name="parameters"></a>Parameter  
 `pStream`  
 [in] Ein Zeiger auf den Stream Marshalling wird.  
  
 `iid`  
 [in] Die GUID der Schnittstelle Marshalling wird.  
  
 `ppUnk`  
 [out] Ein Zeiger auf die Marshalling-Schnittstelle.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein standard HRESULT-Wert.  
  
### <a name="example"></a>Beispiel  
  Siehe das Beispiel für [AtlMarshalPtrInProc](#atlmarshalptrinproc).  
  
## <a name="see-also"></a>Siehe auch  
 [Funktionen](../../atl/reference/atl-functions.md)

