---
title: Registrierungsmakros | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlcom/ATL::_ATL_STATIC_REGISTRY
- atlcom/ATL::DECLARE_LIBID
- atlcom/ATL::DECLARE_NO_REGISTRY
- atlcom/ATL::DECLARE_REGISTRY
- atlcom/ATL::DECLARE_REGISTRY_APPID_RESOURCEID
- atlcom/ATL::DECLARE_REGISTRY_RESOURCE
- atlcom/ATL::DECLARE_REGISTRY_RESOURCEID
dev_langs:
- C++
helpviewer_keywords:
- registry, ATL macros
ms.assetid: 3ee041da-c63b-42a4-89cf-2a4b2a6f81ae
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 56be1e0b5490aa6b6e97b578a7bbf90bcdcca7c8
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/06/2018
ms.locfileid: "37880963"
---
# <a name="registry-macros"></a>Registrierungsmakros
Diese Makros definieren nützlich Typarten-Bibliothek und der Registrierung.  
  
|||  
|-|-|  
|[_ATL_STATIC_REGISTRY](#_atl_static_registry)|Gibt an, dass Sie den Registrierungscode für das Objekt in das Objekt, das eine Abhängigkeit von ATL zu vermeiden. DLL.|  
|[DECLARE_LIBID](#declare_libid)|Bietet eine Möglichkeit für ATL zum Abrufen der *Libid* der Typbibliothek.|  
|[DECLARE_NO_REGISTRY](#declare_no_registry)|Vermeiden Sie die standardmäßige ATL-Registrierung.|  
|[DECLARE_REGISTRY](#declare_registry)|Eintritt, oder das Hauptobjekt Eintrag in der Registrierung entfernt.|  
|[DECLARE_REGISTRY_APPID_RESOURCEID](#declare_registry_appid_resourceid)|Gibt an, die Informationen, die erforderlich sind, für die automatische Registrierung der *Appid*.|  
|[DECLARE_REGISTRY_RESOURCE](#declare_registry_resource)|Die benannte Ressource findet, und führt das Registrierungsskript "darin.|  
|[DECLARE_REGISTRY_RESOURCEID](#declare_registry_resourceid)|Sucht nach der Ressource durch eine ID-Nummer identifiziert und führt das Registrierungsskript "darin.|  

## <a name="requirements"></a>Anforderungen  
 **Header:** atlcom.h  
  
    
##  <a name="_atl_static_registry"></a>  _ATL_STATIC_REGISTRY  
 Ein Symbol, das zeigt an, dass Sie den Registrierungscode für das Objekt in das Objekt, das eine Abhängigkeit ATL zu vermeiden möchten DLL.  
  
```
#define _ATL_STATIC_REGISTRY
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie ATL_STATIC_REGISTRY definieren, sollten Sie den folgenden Code verwenden:  
  
 [!code-cpp[NVC_ATL_EventHandlingSample#5](../../atl/codesnippet/cpp/registry-macros_1.cpp)]  
  
##  <a name="declare_libid"></a>  DECLARE_LIBID  
 Bietet eine Möglichkeit für ATL zum Abrufen der *Libid* der Typbibliothek.  
  
```
DECLARE_LIBID( libid )
```  
  
### <a name="parameters"></a>Parameter  
 *LIBID*  
 Die GUID der Typbibliothek.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie DECLARE_LIBID in einem `CAtlModuleT`-abgeleitete Klasse.  
  
### <a name="example"></a>Beispiel  
 Vom Assistenten generierte ATL-Projekte nicht attributierten müssen ein Beispiel zur Verwendung dieses Makros.  
  
##  <a name="declare_no_registry"></a>  DECLARE_NO_REGISTRY  
 Verwenden Sie DECLARE_NO_REGISTRY, sollten Sie standardmäßige ATL-Registrierung für die Klasse zu vermeiden, in dem dieses Makro angezeigt wird.  
  
```
DECLARE_NO_REGISTRY()
```  
  
##  <a name="declare_registry"></a>  DECLARE_REGISTRY  
 Gibt die standardmäßige klassenregistrierung in der Registrierung des Systems oder entfernt sie aus der Registrierung des Systems.  
  
```
DECLARE_REGISTRY(
    class, 
    pid, 
    vpid, 
    nid, 
    flags )
```  
  
### <a name="parameters"></a>Parameter  
 *class*  
 [in] Aus Gründen der Abwärtskompatibilität enthalten.  
  
 *pid*  
 [in] LPCTSTR, die eine versionsspezifische Programm-ID ist.  
  
 *vpid*  
 [in] LPCTSTR, die eine versionsunabhängige Programm-ID ist.  
  
 *nID*  
 [in] UINT, die einen Index der Ressourcenzeichenfolge in der Registrierung, die als die Beschreibung des Programms verwendet wird.  
  
 *flags*  
 [in] Ein DWORD, das mit des Programms-threading-Modell in der Registrierung. Muss einer der folgenden Werte sein: THREADFLAGS_APARTMENT THREADFLAGS_BOTH oder AUTPRXFLAG.  
  
### <a name="remarks"></a>Hinweise  
 Die standard-Registrierung, bestehen die CLSID, die Programm-ID, die versionsunabhängige Programm-ID, die Zeichenfolge zur fehlerbeschreibung und die Threadmodell ab.  
  
 Wenn Sie ein Objekt erstellen oder Steuern von mit dem ATL-Klassen-Assistenten, der Assistent automatisch implementiert die Unterstützung für skriptbasierte Registrierung und fügt die [DECLARE_REGISTRY_RESOURCEID](#declare_registry_resourceid) Makro, um Ihre Dateien. Wenn Sie Unterstützung für skriptbasierte Registrierung nicht verwenden möchten, müssen Sie dieses Makro mit DECLARE_REGISTRY zu ersetzen. DECLARE_REGISTRY fügt nur die fünf basic-Schlüssel, die oben in der Registrierung. Sie müssen manuell Code zum Einfügen von andere Schlüssel in der Registrierung schreiben.  
  
##  <a name="declare_registry_appid_resourceid"></a>  DECLARE_REGISTRY_APPID_RESOURCEID  
 Gibt an, die Informationen, die erforderlich sind, für die automatische Registrierung der *Appid*.  
  
```
DECLARE_REGISTRY_APPID_RESOURCEID(
    resid, 
    appid )
```  
  
### <a name="parameters"></a>Parameter  
 *"RESID"*  
 Die Ressourcen-Id der RGS-Datei, die Informationen der *Appid*.  
  
 *App-ID*  
 Ein GUID.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie DECLARE_REGISTRY_APPID_RESOURCEID in einem `CAtlModuleT`-abgeleitete Klasse.  
  
### <a name="example"></a>Beispiel  
 Klassen, die ATL-Projekte hinzugefügt, mit dem Assistenten zum Hinzufügen von Klassen-Code werden ein Beispiel zur Verwendung dieses Makros haben.  
  
##  <a name="declare_registry_resource"></a>  DECLARE_REGISTRY_RESOURCE  
 Ruft die benannte Ressource, die mit der Registrierungsdatei ab und führt das Skript aus, um Objekte in der Registrierung des Systems eingeben, oder entfernen sie aus der Registrierung des Systems.  
  
```
DECLARE_REGISTRY_RESOURCE( x )
```  
  
### <a name="parameters"></a>Parameter  
 *w*  
 [in] Die Zeichenfolgen Sie-ID der Ressource.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie ein Objekt erstellen oder Steuern von ATL-Projektassistenten mit, der Assistenten automatisch implementieren die Unterstützung für skriptbasierte Registrierung und Hinzufügen der [DECLARE_REGISTRY_RESOURCEID](#declare_registry_resourceid) Makro, das DECLARE_REGISTRY_ ähnelt Ressource, auf Ihre Dateien.  
  
 Sie können mit der ATL-Registrierungskomponente (Registrar) für den Zugriff auf die optimierte Registrierung statisch verknüpfen. Um zum Registrierungscode statisch zu verknüpfen, fügen Sie die folgende Zeile der Datei "stdafx.h" aus:  
  
 [!code-cpp[NVC_ATL_COM#56](../../atl/codesnippet/cpp/registry-macros_2.h)]  
  
 Wenn Sie ATL Ersatzwerte zur Laufzeit ersetzen möchten, geben Sie das Makro DECLARE_REGISTRY_RESOURCE oder DECLARE_REGISTRY_RESOURCEID nicht. Erstellen Sie stattdessen ein Array von `_ATL_REGMAP_ENTRIES` Strukturen, von denen jeder Eintrag einen Variable Platzhalter enthält mit dem Wert ersetzt den Platzhalter zur Laufzeit zugeordnet. Rufen Sie anschließend [CAtlModule::UpdateRegistryFromResourceD](catlmodule-class.md#updateregistryfromresourced) oder [CAtlModule::UpdateRegistryFromResourceS](catlmodule-class.md#updateregistryfromresources), das Array übergeben. Dadurch werden alle die Ersatzwerte in der `_ATL_REGMAP_ENTRIES` Strukturen, um die Registrierungsstelle Ersatz-Zuordnung.  

  
 Weitere Informationen zu ersetzbare Parameter und Skripts finden Sie im Artikel [der ATL-Registrierungskomponente (Registrar)](../../atl/atl-registry-component-registrar.md).  
  
##  <a name="declare_registry_resourceid"></a>  DECLARE_REGISTRY_RESOURCEID  
 Identisch mit [DECLARE_REGISTRY_RESOURCE](#declare_registry_resource) mit der Ausnahme, dass vom Assistenten generierte UINT verwendet, um die Ressource, anstatt einen Zeichenfolgennamen zu identifizieren.  
  
```
DECLARE_REGISTRY_RESOURCEID( x )
```  
  
### <a name="parameters"></a>Parameter  
 *w*  
 [in] Vom Assistenten generierter Bezeichner der Ressource.  
  
### <a name="remarks"></a>Hinweise  
 Bei der Erstellung eines Objekts oder Steuerelements mithilfe von ATL-Projektassistenten wird automatisch der Assistent implementieren die Unterstützung für skriptbasierte Registrierung und die DECLARE_REGISTRY_RESOURCEID-Makro auf Ihre Dateien hinzufügen.  
  
 Sie können mit der ATL-Registrierungskomponente (Registrar) für den Zugriff auf die optimierte Registrierung statisch verknüpfen. Um zum Registrierungscode statisch zu verknüpfen, fügen Sie die folgende Zeile der Datei "stdafx.h" aus:  
  
 [!code-cpp[NVC_ATL_COM#56](../../atl/codesnippet/cpp/registry-macros_2.h)]  
  
 Wenn Sie ATL Ersatzwerte zur Laufzeit ersetzen möchten, geben Sie das Makro DECLARE_REGISTRY_RESOURCE oder DECLARE_REGISTRY_RESOURCEID nicht. Erstellen Sie stattdessen ein Array von `_ATL_REGMAP_ENTRIES` Strukturen, von denen jeder Eintrag einen Variable Platzhalter enthält mit dem Wert ersetzt den Platzhalter zur Laufzeit zugeordnet. Rufen Sie anschließend [CAtlModule::UpdateRegistryFromResourceD](catlmodule-class.md#updateregistryfromresourced) oder [CAtlModule::UpdateRegistryFromResourceS](catlmodule-class.md#updateregistryfromresources), das Array übergeben. Dadurch werden alle die Ersatzwerte in der `_ATL_REGMAP_ENTRIES` Strukturen, um die Registrierungsstelle Ersatz-Zuordnung.  

  
 Weitere Informationen zu ersetzbare Parameter und Skripts finden Sie im Artikel [der ATL-Registrierungskomponente (Registrar)](../../atl/atl-registry-component-registrar.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Makros](../../atl/reference/atl-macros.md)
