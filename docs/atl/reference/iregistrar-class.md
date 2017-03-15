---
title: IRegistrar-Schnittstelle | Microsoft-Dokumentation
ms.custom: 
ms.date: 2/1/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::IRegistrar
- IRegistrar
dev_langs:
- C++
helpviewer_keywords:
- Iregistrar Interface
ms.assetid: e88c04b7-0c93-4ae8-aeb9-ecd78f87421e
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
ms.sourcegitcommit: 199cdfd91a7d1b9882b57118c852352f6fdda43e
ms.openlocfilehash: e73e095d253d5ec5ca53e4e446019b2da79e5d39
ms.lasthandoff: 02/24/2017

---
# <a name="iregistrar-interface"></a>IRegistrar-Schnittstelle
Diese Schnittstelle ist konnte IRegistrar definiert und wird intern verwendet, durch die Memberfunktionen von CAtlModule wie z. B. [UpdateRegistryFromResourceD](catlmodule-class.md#updateregistryfromresourced).   
  
## <a name="syntax"></a>Syntax  
  
```
typedef interface IRegistrar IRegistrar;
```  
## <a name="remarks"></a>Hinweise
Finden Sie unter [mithilfe von ersetzbaren Parametern (die Registrierungsstelle Präprozessor)](../../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md) für weitere Details.  

## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[IRegistrar::ResourceRegisterSz](#resourceregistersz)|Registriert die. |  
|[IRegistrar::ResourceUnregisterSz](#resourceunregistersz)| Hebt die Registrierung der Ressourcenanbieters.|  
|[IRegistrar::FileRegister](#fileregister)|Registriert die Datei.|  
|[IRegistrar::FileUnregister](#fileunregister)|Hebt die Registrierung der das.|  
|[IRegistrar::StringRegister](#stringregister)|Registriert die Zeichenfolge an.|  
|[IRegistrar::StringUnregister](#stringunregister)|Hebt die Registrierung der Zeichenfolge|  
|[IRegistrar::ResourceRegister](#resourceregister)|Registriert die.|  
|[IRegistrar::ResourceUnregister](#resourceunregister)|Hebt die Registrierung der Ressourcenanbieters.| 
  

 
## <a name="requirements"></a>Anforderungen  
 **Header:** atlifase.h  
  
##  <a name="a-nameresourceregistersza--iregistrarresourceregistersz"></a><a name="resourceregistersz"></a>IRegistrar::ResourceRegisterSz 
 Registriert die.  
  
```
virtual HRESULT STDMETHODCALLTYPE ResourceRegisterSz( 
    /* [in] */ _In_z_ LPCOLESTR resFileName,
    /* [in] */ _In_z_ LPCOLESTR szID,
    /* [in] */ _In_z_ LPCOLESTR szType) = 0;
```  
  
 
  
##  <a name="a-nameresourceunregistersza--iregistrarresourceunregistersz"></a><a name="resourceunregistersz"></a>IRegistrar::ResourceUnregisterSz  
 Hebt die Registrierung der Ressourcenanbieters.
  
```
virtual HRESULT STDMETHODCALLTYPE ResourceUnregisterSz( 
    /* [in] */ _In_z_ LPCOLESTR resFileName,
    /* [in] */ _In_z_ LPCOLESTR szID,
    /* [in] */ _In_z_ LPCOLESTR szType) = 0;
```  
  
  
##  <a name="a-namefileregistera--iregistrarfileregister"></a><a name="fileregister"></a>IRegistrar::FileRegister  
Registriert die Datei.
  
```
virtual HRESULT STDMETHODCALLTYPE FileRegister( 
    /* [in] */ _In_z_ LPCOLESTR fileName) = 0;
```  
  
  
##  <a name="a-namefileunregistera--iregistrarfileunregister"></a><a name="fileunregister"></a>IRegistrar::FileUnregister  
Hebt die Registrierung der das.

```
virtual HRESULT STDMETHODCALLTYPE FileUnregister( 
    */ _In_z_ LPCOLESTR fileName) = 0;
```  
  
 
##  <a name="a-namestringregistera--iregistrarstringregister"></a><a name="stringregister"></a>IRegistrar::StringRegister  
  Registriert die Daten der angegebenen Zeichenfolge.
```
virtual HRESULT STDMETHODCALLTYPE StringRegister( 
    /* [in] */ _In_z_ LPCOLESTR data) = 0;
```  
  
##  <a name="a-namestringunregistera--iregistrarstringunregister"></a><a name="stringunregister"></a>IRegistrar::StringUnregister
 Hebt die Registrierung die Daten der angegebenen Zeichenfolge.  
  
```
virtualHRESULT STDMETHODCALLTYPE StringUnregister( 
    /* [in] */ _In_z_ LPCOLESTR data) = 0;
```  

  
##  <a name="a-nameresourceregistera--iregistrarresourceregister"></a><a name="resourceregister"></a>IRegistrar::ResourceRegister  
 Registriert die.  
  
```
virtual HRESULT STDMETHODCALLTYPE ResourceRegister( 
    /* [in] */ _In_z_ LPCOLESTR resFileName,
    /* [in] */ _In_ UINT nID,
    /* [in] */ _In_z_ LPCOLESTR szType) = 0;
```  
   
  
##  <a name="a-nameresourceunregistera--iregistrarresourceunregister"></a><a name="resourceunregister"></a>IRegistrar::ResourceUnregister  
 Hebt die Registrierung der Ressourcenanbieters.  
  
```
virtualHRESULT STDMETHODCALLTYPE ResourceUnregister( 
    /* [in] */ _In_z_ LPCOLESTR resFileName,
    /* [in] */ _In_ UINT nID,
    /* [in] */ _In_z_ LPCOLESTR szType) = 0; 
```  
 
## <a name="see-also"></a>Siehe auch  
 [Mithilfe von ersetzbaren Parametern (die Registrierungsstelle Präprozessor)](../../atl/using-replaceable-parameters-the-registrar-s-preprocessor.md)  
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)   
 [Modulklassen](../../atl/atl-module-classes.md)   
 [Registrierungskomponente (Registrar)](../../atl/atl-registry-component-registrar.md)  

