---
title: Registrierung Makros | Microsoft Docs
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
ms.openlocfilehash: ed9b172217f1ca7ada7d8752151126b53055df37
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/03/2018
---
# <a name="registry-macros"></a>Registrierung-Makros
Diese Makros definieren nützlicher Bibliothek und die Registrierung Einrichtungen.  
  
|||  
|-|-|  
|[_ATL_STATIC_REGISTRY](#_atl_static_registry)|Gibt an, dass die Registrierungscode für das Objekt in das Objekt, das eine Abhängigkeit zu ATL vermieden werden soll DLL.|  
|[DECLARE_LIBID](#declare_libid)|Bietet eine Möglichkeit für ATL zum Abrufen der *Libid* der Typbibliothek.|  
|[DECLARE_NO_REGISTRY](#declare_no_registry)|Vermeidet Standard ATL-Registrierung.|  
|[DECLARE_REGISTRY](#declare_registry)|Eingibt, oder das Hauptobjekt Eintrag in der Registrierung entfernt.|  
|[DECLARE_REGISTRY_APPID_RESOURCEID](#declare_registry_appid_resourceid)|Gibt an, die Informationen erforderlich, um die automatische Registrierung der *Appid*.|  
|[DECLARE_REGISTRY_RESOURCE](#declare_registry_resource)|Die benannte Ressource findet, und führt das Registrierungsskript darin.|  
|[DECLARE_REGISTRY_RESOURCEID](#declare_registry_resourceid)|Sucht nach der Ressource durch eine ID-Nummer identifiziert und das Registrierungsskript darin ausgeführt.|  

## <a name="requirements"></a>Anforderungen  
 **Header:** atlcom.h  
  
    
##  <a name="_atl_static_registry"></a>  _ATL_STATIC_REGISTRY  
 Ein Symbol, der angibt, dass die Registrierungscode für das Objekt in das Objekt, das eine Abhängigkeit zu ATL vermieden werden soll DLL.  
  
```
#define _ATL_STATIC_REGISTRY
```  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie definieren **ATL_STATIC_REGISTRY**, sollten Sie den folgenden Code verwenden:  
  
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
 Verwendung `DECLARE_LIBID` in einem `CAtlModuleT`-Klasse.  
  
### <a name="example"></a>Beispiel  
 Vom Assistenten generierten ATL-Projekte nicht attributiert werden ein Beispiel zur Verwendung dieses Makro haben.  
  
##  <a name="declare_no_registry"></a>  DECLARE_NO_REGISTRY  
 Verwendung `DECLARE_NO_REGISTRY` gegebenenfalls alle Standard-ATL-Registrierung für die Klasse zu vermeiden, in denen dieses Makro wird angezeigt.  
  
```
DECLARE_NO_REGISTRY()
```  
  
##  <a name="declare_registry"></a>  DECLARE_REGISTRY  
 Die standardmäßige Klasse-Registrierung in der systemregistrierung eingibt, oder aus der Registrierung entfernt.  
  
```
DECLARE_REGISTRY(
    class, 
    pid, 
    vpid, 
    nid, 
    flags )
```  
  
### <a name="parameters"></a>Parameter  
 `class`  
 [in] Aus Gründen der Abwärtskompatibilität.  
  
 `pid`  
 [in] Ein `LPCTSTR` also ein versionsspezifisches Programmbezeichner.  
  
 *vpid*  
 [in] Ein `LPCTSTR` also eine versionsunabhängige Programm-Bezeichner.  
  
 *nID*  
 [in] Ein **"uint"** also einen Index der Ressourcenzeichenfolge in der Registrierung, die als die Beschreibung des Programms verwendet.  
  
 `flags`  
 [in] Ein `DWORD` mit dem Programm die Threadingmodell in der Registrierung. Muss einen der folgenden Werte sein: **THREADFLAGS_APARTMENT**, **THREADFLAGS_BOTH**, oder **AUTPRXFLAG**.  
  
### <a name="remarks"></a>Hinweise  
 Die standard-Registrierung besteht aus der CLSID, Programm-ID, versionsunabhängige Programm-ID, Beschreibung und Threadmodell.  
  
 Wenn Sie ein Objekt erstellen oder ein Steuerelement mit dem ATL-Klassen-Assistenten, der Assistent automatisch implementiert die Unterstützung der Registrierung basierende und fügt die [DECLARE_REGISTRY_RESOURCEID](#declare_registry_resourceid) Makro auf Ihre Dateien. Wenn Sie nicht skriptbasierten Registrierung Unterstützung wünschen, müssen Sie dieses Makro mit ersetzen `DECLARE_REGISTRY`. `DECLARE_REGISTRY` Fügt nur die fünf grundlegenden Schlüssel, der oben beschriebenen, in der Registrierung. Sie müssen Code zum Einfügen der andere Schlüssel in der Registrierung manuell schreiben.  
  
##  <a name="declare_registry_appid_resourceid"></a>  DECLARE_REGISTRY_APPID_RESOURCEID  
 Gibt an, die Informationen erforderlich, um die automatische Registrierung der *Appid*.  
  
```
DECLARE_REGISTRY_APPID_RESOURCEID(
    resid, 
    appid )
```  
  
### <a name="parameters"></a>Parameter  
 *RESID*  
 Die Ressourcen-Id der RGS-Datei, die Informationen der *Appid*.  
  
 *AppID*  
 Ein GUID.  
  
### <a name="remarks"></a>Hinweise  
 Verwendung `DECLARE_REGISTRY_APPID_RESOURCEID` in einem `CAtlModuleT`-Klasse.  
  
### <a name="example"></a>Beispiel  
 Klassen, die hinzugefügt, ATL-Projekte mit der Klasse hinzufügen-Code-Assistenten werden ein Beispiel zur Verwendung dieses Makro haben.  
  
##  <a name="declare_registry_resource"></a>  DECLARE_REGISTRY_RESOURCE  
 Ruft die benannte Ressource, die die Registrierungsdatei enthält, und führt das Skript aus, um Objekte in der systemregistrierung eingeben oder aus der Registrierung zu entfernen.  
  
```
DECLARE_REGISTRY_RESOURCE( x )
```  
  
### <a name="parameters"></a>Parameter  
 *w*  
 [in] Zeichenfolgen Sie-ID der Ressource.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie ein Objekt erstellen oder steuern, mit dem ATL-Projekt-Assistenten, der Assistent automatisch implementieren die Unterstützung der Registrierung basierende und Hinzufügen der [DECLARE_REGISTRY_RESOURCEID](#declare_registry_resourceid) -Makro, das ähnelt `DECLARE_REGISTRY_RESOURCE`in Ihre Dateien.  
  
 Sie können statisch mit der ATL-Registrierungskomponente (Registrar) für optimierte Registrierungszugriff verknüpfen. Fügen Sie die folgende Zeile in der Datei "stdafx.h", um statisch mit der Registrierungsstelle Code zu verknüpfen:  
  
 [!code-cpp[NVC_ATL_COM#56](../../atl/codesnippet/cpp/registry-macros_2.h)]  
  
 Wenn Sie ATL Ersatzwerte zur Laufzeit ersetzen möchten, geben Sie keine der `DECLARE_REGISTRY_RESOURCE` oder `DECLARE_REGISTRY_RESOURCEID` Makro. Erstellen Sie stattdessen ein Array von **_ATL_REGMAP_ENTRIES** Strukturen, wobei jeder Eintrag einen Variablen Platzhalter enthält gekoppelt mit einem Wert zur Laufzeit den Platzhalter ersetzen. Rufen Sie anschließend [CAtlModule::UpdateRegistryFromResourceD](catlmodule-class.md#updateregistryfromresourced) oder [CAtlModule::UpdateRegistryFromResourceS](catlmodule-class.md#updateregistryfromresources), übergeben Sie das Array. Dies fügt alle die Ersatzwerte in der **_ATL_REGMAP_ENTRIES** Strukturen, die die Registrierungsstelle Ersatz-Zuordnung.  

  
 Weitere Informationen zu ersetzbare Parameter und scripting finden Sie im Artikel [der ATL-Registrierungskomponente (Registrar)](../../atl/atl-registry-component-registrar.md).  
  
##  <a name="declare_registry_resourceid"></a>  DECLARE_REGISTRY_RESOURCEID  
 Identisch mit [DECLARE_REGISTRY_RESOURCE](#declare_registry_resource) identisch, jedoch eine vom Assistenten generierten verwendet **"uint"** ein Zeichenfolgenname, anstatt die Ressource identifiziert.  
  
```
DECLARE_REGISTRY_RESOURCEID( x )
```  
  
### <a name="parameters"></a>Parameter  
 *w*  
 [in] Vom Assistenten generierten Bezeichner der Ressource.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie ein Objekt erstellen oder steuern, mit dem ATL-Projekt-Assistenten, der Assistent automatisch implementieren die Unterstützung der Registrierung basierende und Hinzufügen der `DECLARE_REGISTRY_RESOURCEID` Makro auf Ihre Dateien.  
  
 Sie können statisch mit der ATL-Registrierungskomponente (Registrar) für optimierte Registrierungszugriff verknüpfen. Fügen Sie die folgende Zeile in der Datei "stdafx.h", um statisch mit der Registrierungsstelle Code zu verknüpfen:  
  
 [!code-cpp[NVC_ATL_COM#56](../../atl/codesnippet/cpp/registry-macros_2.h)]  
  
 Wenn Sie ATL Ersatzwerte zur Laufzeit ersetzen möchten, geben Sie keine der `DECLARE_REGISTRY_RESOURCE` oder `DECLARE_REGISTRY_RESOURCEID` Makro. Erstellen Sie stattdessen ein Array von **_ATL_REGMAP_ENTRIES** Strukturen, wobei jeder Eintrag einen Variablen Platzhalter enthält gekoppelt mit einem Wert zur Laufzeit den Platzhalter ersetzen. Rufen Sie anschließend [CAtlModule::UpdateRegistryFromResourceD](catlmodule-class.md#updateregistryfromresourced) oder [CAtlModule::UpdateRegistryFromResourceS](catlmodule-class.md#updateregistryfromresources), übergeben Sie das Array. Dies fügt alle die Ersatzwerte in der **_ATL_REGMAP_ENTRIES** Strukturen, die die Registrierungsstelle Ersatz-Zuordnung.  

  
 Weitere Informationen zu ersetzbare Parameter und scripting finden Sie im Artikel [der ATL-Registrierungskomponente (Registrar)](../../atl/atl-registry-component-registrar.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Makros](../../atl/reference/atl-macros.md)
