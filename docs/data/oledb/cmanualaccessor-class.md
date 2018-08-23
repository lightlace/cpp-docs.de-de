---
title: CManualAccessor-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL::CManualAccessor
- ATL.CManualAccessor
- CManualAccessor
- ATL::CManualAccessor::AddBindEntry
- ATL.CManualAccessor.AddBindEntry
- CManualAccessor::AddBindEntry
- AddBindEntry
- CManualAccessor.AddBindEntry
- CManualAccessor::AddParameterEntry
- ATL.CManualAccessor.AddParameterEntry
- CManualAccessor.AddParameterEntry
- AddParameterEntry
- ATL::CManualAccessor::AddParameterEntry
- ATL::CManualAccessor::CreateAccessor
- CreateAccessor
- ATL.CManualAccessor.CreateAccessor
- CManualAccessor.CreateAccessor
- CManualAccessor::CreateAccessor
- ATL::CManualAccessor::CreateParameterAccessor
- ATL.CManualAccessor.CreateParameterAccessor
- CManualAccessor.CreateParameterAccessor
- CreateParameterAccessor
- CManualAccessor::CreateParameterAccessor
dev_langs:
- C++
helpviewer_keywords:
- CManualAccessor class
- AddBindEntry method
- AddParameterEntry method
- CreateAccessor method
- CreateParameterAccessor method
ms.assetid: a0088074-7135-465c-b228-69097a50b8cc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 59bc14040e9dfc7ba69d95525bae7ad795de43b8
ms.sourcegitcommit: a41c4d096afca1e9b619bbbce045b77135d32ae2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2018
ms.locfileid: "42575486"
---
# <a name="cmanualaccessor-class"></a>CManualAccessor-Klasse
Stellt einen Accessor für die erweiterte Verwendung vorgesehen.  
  
## <a name="syntax"></a>Syntax

```cpp
class CManualAccessor : public CAccessorBase  
```  

## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="members"></a>Member  
  
### <a name="methods"></a>Methoden  
  
|||  
|-|-|  
|[AddBindEntry](#addbindentry)|Fügt eine Bindung für den Ausgabespalten.|  
|[AddParameterEntry](#addparameterentry)|Fügt einen Parametereintrag, die dem Parameteraccessor.|  
|[CreateAccessor](#createaccessor)|Belegt Speicher für die Spalte binden, Strukturen und der Spaltenelemente für die Daten initialisiert.|  
|[CreateParameterAccessor](#createparameteraccessor)|Belegt Speicher für den Parameter binden Strukturen und initialisiert die Datenmember des Parameters.|  
  
## <a name="remarks"></a>Hinweise  
 Mithilfe von `CManualAccessor`, können Sie den Parameter angeben und ausgabebindung Spalte von Run-Time-Funktionsaufrufen.  

## <a name="addbindentry"></a> CManualAccessor:: AddBindEntry
Fügt eine Bindung für den Ausgabespalten.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
void AddBindEntry(DBORDINAL nOrdinal,  
   DBTYPE wType,  DBLENGTH nColumnSize,  
   void* pData,  
   void* pLength = NULL,  
   void* pStatus = NULL) throw ();  
```  
  
#### <a name="parameters"></a>Parameter  
 Finden Sie unter [DBBINDING](/previous-versions/windows/desktop/ms716845\(v=vs.85\)) in die *OLE DB-Programmierreferenz*.  
  
 *nOrdinal*  
 [in] Nummer der Spalte.  
  
 *wType*  
 [in] -Datentyp.  
  
 *nColumnSize*  
 [in] Spaltengröße in Bytes.  
  
 *pData*  
 [in] Ein Zeiger auf die Daten der Spalte im Puffer gespeichert.  
  
 *pLength*  
 [in] Ein Zeiger auf die Feldlänge, falls erforderlich.  
  
 *pStatus*  
 [in] Ein Zeiger auf die Variable an den Status der Spalte gebunden werden soll, falls erforderlich.  
  
### <a name="remarks"></a>Hinweise  
 Um diese Funktion verwenden zu können, müssen Sie zuerst Aufrufen [CreateAccessor](../../data/oledb/cmanualaccessor-createaccessor.md). Fügen Sie können nicht mehrere Einträge als die Anzahl der Spalten, die im angegebenen `CreateAccessor`. 
  
## <a name="addparameterentry"></a> CManualAccessor:: AddParameterEntry
Die Parameter-Eintrag-Strukturen wird ein Parametereintrag hinzugefügt.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
void AddParameterEntry(DBORDINAL nOrdinal,  
   DBTYPE wType,  DBLENGTH nColumnSize,  
   void* pData,  
   void* pLength = NULL,  
   void* pStatus = NULL,  
   DBPARAMIO eParamIO = DBPARAMIO_INPUT) throw ();  
```  
  
#### <a name="parameters"></a>Parameter  
 Finden Sie unter [DBBINDING](/previous-versions/windows/desktop/ms716845\(v=vs.85\)) in die *OLE DB-Programmierreferenz*.  
  
 *nOrdinal*  
 [in] Parameteranzahl.  
  
 *wType*  
 [in] -Datentyp.  
  
 *nColumnSize*  
 [in] Spaltengröße in Bytes.  
  
 *pData*  
 [in] Ein Zeiger auf die Daten der Spalte im Puffer gespeichert.  
  
 *pLength*  
 [in] Ein Zeiger auf die Feldlänge, falls erforderlich.  
  
 *pStatus*  
 [in] Ein Zeiger auf die Variable an den Status der Spalte gebunden werden soll, falls erforderlich.  
  
 *eParamIO*  
 [in] Gibt an, ob der Parameter mit dem die Bindung verknüpft ist ein Eingabe-, Eingabe/Ausgabe- oder Ausgabe-Parameter.  
  
### <a name="remarks"></a>Hinweise  
 Um diese Funktion verwenden zu können, müssen Sie zuerst Aufrufen [CreateParameterAccessor](../../data/oledb/cmanualaccessor-createparameteraccessor.md). 

## <a name="createaccessor"></a> CManualAccessor:: CreateAccessor
Belegt Speicher für die Spalte binden, Strukturen und der Spaltenelemente für die Daten initialisiert.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
HRESULT CreateAccessor(int nBindEntries,   
  void* pBuffer,   
   DBLENGTH nBufferSize) throw();  
```  
  
#### <a name="parameters"></a>Parameter  
 *nBindEntries*  
 [in] Anzahl der Spalten. Diese Anzahl sollte die Anzahl der Aufrufe entsprechen den [CManualAccessor:: AddBindEntry](../../data/oledb/cmanualaccessor-addbindentry.md) Funktion.  
  
 *pBuffer*  
 [in] Ein Zeiger auf den Puffer, in denen die Ausgabespalten gespeichert sind.  
  
 *nBufferSize*  
 [in] Die Größe des Puffers in Byte.  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der standardmäßigen HRESULT-Werte.  
  
### <a name="remarks"></a>Hinweise  
 Rufen Sie diese Funktion vor dem Aufruf der `CManualAccessor::AddBindEntry` Funktion.  

## <a name="createparameteraccessor"></a> CManualAccessor:: Createparameteraccessor
Belegt Speicher für den Parameter binden Strukturen und initialisiert die Datenmember des Parameters.  
  
### <a name="syntax"></a>Syntax  
  
```cpp
HRESULT CreateParameterAccessor(int nBindEntries,   
   void* pBuffer,   
   DBLENGTH nBufferSize) throw();  
```  
  
#### <a name="parameters"></a>Parameter  
 *nBindEntries*  
 [in] Anzahl der Spalten.  
  
 *pBuffer*  
 [in] Ein Zeiger auf den Puffer, in denen die Eingabespalten gespeichert sind.  
  
 *nBufferSize*  
 [in] Die Größe des Puffers in Byte.  
  
### <a name="return-value"></a>Rückgabewert  
 Einer der standardmäßigen HRESULT-Werte.  
  
### <a name="remarks"></a>Hinweise  
 Sie müssen diese Funktion vor dem Aufruf aufrufen [AddParameterEntry](../../data/oledb/cmanualaccessor-addparameterentry.md).

## <a name="see-also"></a>Siehe auch  
 [DBViewer](../../visual-cpp-samples.md)   
 [OLE DB-Consumervorlagen](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Referenz der OLE DB Consumervorlagen](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [CAccessor-Klasse](../../data/oledb/caccessor-class.md)   
 [CDynamicAccessor-Klasse](../../data/oledb/cdynamicaccessor-class.md)   
 [CDynamicParameterAccessor-Klasse](../../data/oledb/cdynamicparameteraccessor-class.md)