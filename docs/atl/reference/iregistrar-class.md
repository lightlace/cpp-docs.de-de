---
title: IRegistrar Schnittstelle | Microsoft Docs
ms.custom: 
ms.date: 2/1/2017
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IRegistrar
- ATLIFASE/ATL::IRegistrar
- ATLIFASE/ATL::IRegistrar::ResourceRegisterSz
- ATLIFASE/ATL::IRegistrar::ResourceUnregisterSz
- ATLIFASE/ATL::IRegistrar::FileRegister
- ATLIFASE/ATL::IRegistrar::FileUnregister
- ATLIFASE/ATL::IRegistrar::StringRegister
- ATLIFASE/ATL::IRegistrar::StringUnregister
- ATLIFASE/ATL::IRegistrar::ResourceRegister
- ATLIFASE/ATL::IRegistrar::ResourceUnregister
dev_langs: C++
helpviewer_keywords: Iregistrar Interface
ms.assetid: e88c04b7-0c93-4ae8-aeb9-ecd78f87421e
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6c0b304b00b5cc5c613ff7e81818d1c637989e5f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="iregistrar-interface"></a>IRegistrar-Schnittstelle
Diese Schnittstelle wird konnte IRegistrar definiert und wird intern verwendet von Memberfunktionen von CAtlModule wie z. B. [UpdateRegistryFromResourceD](catlmodule-class.md#updateregistryfromresourced).   
  
## <a name="syntax"></a>Syntax  
  
```
typedef interface IRegistrar IRegistrar;
```  
## <a name="remarks"></a>Hinweise
Finden Sie im Thema [mithilfe von ersetzbaren Parametern (die Registrierungsstelle Präprozessor)](../../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md) Weitere Details.  

## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IRegistrar::ResourceRegisterSz](#resourceregistersz)|Registriert die Ressource an. |  
|[IRegistrar::ResourceUnregisterSz](#resourceunregistersz)| Hebt die Registrierung der Ressourcenanbieters.|  
|[IRegistrar::FileRegister](#fileregister)|Registriert die Datei.|  
|[IRegistrar::FileUnregister](#fileunregister)|Hebt die Registrierung der das.|  
|[IRegistrar::StringRegister](#stringregister)|Registriert die Zeichenfolge an.|  
|[IRegistrar::StringUnregister](#stringunregister)|Hebt die Registrierung der Zeichenfolge|  
|[IRegistrar::ResourceRegister](#resourceregister)|Registriert die Ressource an.|  
|[IRegistrar::ResourceUnregister](#resourceunregister)|Hebt die Registrierung der Ressourcenanbieters.| 
  

 
## <a name="requirements"></a>Anforderungen  
 **Header:** atlifase.h  
  
##  <a name="resourceregistersz"></a>IRegistrar::ResourceRegisterSz 
 Registriert die Ressource an.  
  
```
virtual HRESULT STDMETHODCALLTYPE ResourceRegisterSz( 
    /* [in] */ _In_z_ LPCOLESTR resFileName,
    /* [in] */ _In_z_ LPCOLESTR szID,
    /* [in] */ _In_z_ LPCOLESTR szType) = 0;
```  
  
 
  
##  <a name="resourceunregistersz"></a>IRegistrar::ResourceUnregisterSz  
 Hebt die Registrierung der Ressourcenanbieters.
  
```
virtual HRESULT STDMETHODCALLTYPE ResourceUnregisterSz( 
    /* [in] */ _In_z_ LPCOLESTR resFileName,
    /* [in] */ _In_z_ LPCOLESTR szID,
    /* [in] */ _In_z_ LPCOLESTR szType) = 0;
```  
  
  
##  <a name="fileregister"></a>IRegistrar::FileRegister  
Registriert die Datei.
  
```
virtual HRESULT STDMETHODCALLTYPE FileRegister( 
    /* [in] */ _In_z_ LPCOLESTR fileName) = 0;
```  
  
  
##  <a name="fileunregister"></a>IRegistrar::FileUnregister  
Hebt die Registrierung der das.

```
virtual HRESULT STDMETHODCALLTYPE FileUnregister( 
    */ _In_z_ LPCOLESTR fileName) = 0;
```  
  
 
##  <a name="stringregister"></a>IRegistrar::StringRegister  
  Registriert die angegebene Zeichenfolgendaten an.
```
virtual HRESULT STDMETHODCALLTYPE StringRegister( 
    /* [in] */ _In_z_ LPCOLESTR data) = 0;
```  
  
##  <a name="stringunregister"></a>IRegistrar::StringUnregister
 Hebt die Registrierung der angegebenen Zeichenfolgendaten.  
  
```
virtualHRESULT STDMETHODCALLTYPE StringUnregister( 
    /* [in] */ _In_z_ LPCOLESTR data) = 0;
```  

  
##  <a name="resourceregister"></a>IRegistrar::ResourceRegister  
 Registriert die Ressource an.  
  
```
virtual HRESULT STDMETHODCALLTYPE ResourceRegister( 
    /* [in] */ _In_z_ LPCOLESTR resFileName,
    /* [in] */ _In_ UINT nID,
    /* [in] */ _In_z_ LPCOLESTR szType) = 0;
```  
   
  
##  <a name="resourceunregister"></a>IRegistrar::ResourceUnregister  
 Hebt die Registrierung der Ressourcenanbieters.  
  
```
virtualHRESULT STDMETHODCALLTYPE ResourceUnregister( 
    /* [in] */ _In_z_ LPCOLESTR resFileName,
    /* [in] */ _In_ UINT nID,
    /* [in] */ _In_z_ LPCOLESTR szType) = 0; 
```  
 
## <a name="see-also"></a>Siehe auch  
 [Verwenden von ersetzbaren Parametern (Der Registrierungspräprozessor)](../../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md)  
 [Klassenübersicht](../../atl/atl-class-overview.md)   
 [Modulklassen](../../atl/atl-module-classes.md)   
 [Registrierungskomponente (Registrar)](../../atl/atl-registry-component-registrar.md)  
