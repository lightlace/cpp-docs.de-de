---
title: 'CDBPropSet:: AddProperty | Microsoft Docs'
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDBPropSet::AddProperty
- CDBPropSet.AddProperty
- AddProperty
- ATL::CDBPropSet::AddProperty
- ATL.CDBPropSet.AddProperty
dev_langs: C++
helpviewer_keywords: AddProperty method
ms.assetid: dc9539d3-1ee4-40f3-9281-2068e6d65e93
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: fa9c2d979bc98ebac543f0b17c7afdce2ab5f59b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="cdbpropsetaddproperty"></a>CDBPropSet::AddProperty
Fügt eine Eigenschaft zum Eigenschaftensatz.  
  
## <a name="syntax"></a>Syntax  
  
```  
  
      bool AddProperty(   
   DWORD dwPropertyID,   
   const VARIANT& var,   
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
) throw( );  
bool AddProperty(  
   DWORD dwPropertyID,  
   LPCSTR szValue,  
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
) throw( );  
bool AddProperty(  
   DWORD dwPropertyID,  
   LPCWSTR szValue,   
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
) throw( );  
bool AddProperty(  
   DWORD dwPropertyID,  
   bool bValue,  
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
) throw( );  
bool AddProperty(  
   DWORD dwPropertyID,  
   BYTE bValue,  
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
);  
bool AddProperty(  
   DWORD dwPropertyID,  
   short nValue,  
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
);  
bool AddProperty(  
   DWORD dwPropertyID,  
   long nValue,  
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
);  
bool AddProperty(  
   DWORD dwPropertyID,  
   float fltValue,  
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
);  
bool AddProperty(  
   DWORD dwPropertyID,  
   double dblValue,  
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
) throw( );  
bool AddProperty(  
   DWORD dwPropertyID,  
   CY cyValue,  
   DBPROPOPTIONS propoptions = DBPROPOPTIONS_REQUIRED    
) throw( );  
```  
  
#### <a name="parameters"></a>Parameter  
 *dwPropertyID*  
 [in] Die ID der Eigenschaft hinzugefügt werden. Zum Initialisieren der **DwPropertyID** von der `DBPROP` Struktur hinzugefügt, das die Eigenschaft festgelegt.  
  
 `var`  
 [in] Eine Variante, die zur Initialisierung des Eigenschaftswert für die `DBPROP` Struktur hinzugefügt, das die Eigenschaft festgelegt.  
  
 `szValue`  
 [in] Eine Zeichenfolge, die zur Initialisierung des Eigenschaftswert für die `DBPROP` Struktur hinzugefügt, das die Eigenschaft festgelegt.  
  
 `bValue`  
 [in] Ein **BYTE** oder ein boolescher Wert, der zum Initialisieren des Eigenschaftswert für die `DBPROP` Struktur hinzugefügt, das die Eigenschaft festgelegt.  
  
 `nValue`  
 [in] Ein Ganzzahlwert verwendet, um den Eigenschaftswert für Initialisieren der `DBPROP` Struktur hinzugefügt, das die Eigenschaft festgelegt.  
  
 *fltValue*  
 [in] Ein Gleitkommawert, der zum Initialisieren des Eigenschaftswert für die `DBPROP` Struktur hinzugefügt, das die Eigenschaft festgelegt.  
  
 `dblValue`  
 [in] Ein Gleitkommawert mit doppelter Genauigkeit, der zur Initialisierung des Eigenschaftswert für die `DBPROP` Struktur hinzugefügt, das die Eigenschaft festgelegt.  
  
 `cyValue`  
 [in] CY Währungswert verwendet, um den Eigenschaftswert für Initialisieren der `DBPROP` Struktur hinzugefügt, das die Eigenschaft festgelegt.  
  
## <a name="return-value"></a>Rückgabewert  
 **"true"** , wenn die Eigenschaft erfolgreich hinzugefügt wurde. andernfalls **"false"**.  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atldbcli.h  
  
## <a name="see-also"></a>Siehe auch  
 [CDBPropSet-Klasse](../../data/oledb/cdbpropset-class.md)   
 [DBPROP-Struktur](https://msdn.microsoft.com/en-us/library/ms717970.aspx)