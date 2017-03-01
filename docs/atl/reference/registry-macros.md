---
title: Registrierung Makros | Microsoft-Dokumentation
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
helpviewer_keywords:
- registry, ATL macros
ms.assetid: 3ee041da-c63b-42a4-89cf-2a4b2a6f81ae
caps.latest.revision: 16
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 3a3abf5ad29b50c7f6708f02fd7c5aa193b3591c
ms.lasthandoff: 02/24/2017

---
# <a name="registry-macros"></a>Registrierung von Makros
Diese Makros definieren nützlicher Funktionen für Bibliothek und Registrierung.  
  
|||  
|-|-|  
|[_ATL_STATIC_REGISTRY](#_atl_static_registry)|Gibt an, dass Sie den Code zur Registrierung für das Objekt in das Objekt, das eine Abhängigkeit von ATL vermeiden möchten DLL.|  
|[DECLARE_LIBID](#declare_libid)|Bietet eine Möglichkeit für ATL zum Abrufen der *Libid* der Typbibliothek.|  
|[DECLARE_NO_REGISTRY](#declare_no_registry)|Vermeidet Standard ATL-Registrierung.|  
|[DECLARE_REGISTRY](#declare_registry)|Eingibt oder das Hauptobjekt-Eintrag in der Registrierung entfernt.|  
|[DECLARE_REGISTRY_APPID_RESOURCEID](#declare_registry_appid_resourceid)|Gibt an, die Angaben zur automatischen Registrierung der *Appid*.|  
|[DECLARE_REGISTRY_RESOURCE](#declare_registry_resource)|Sucht die benannte Ressource und das Registrierungsskript darin ausgeführt.|  
|[DECLARE_REGISTRY_RESOURCEID](#declare_registry_resourceid)|Sucht nach der Ressource durch eine ID-Nummer identifiziert und das Registrierungsskript darin ausgeführt.|  

## <a name="requirements"></a>Anforderungen  
 **Header:** Standardschnittstellen  
  
    
##  <a name="a-nameatlstaticregistrya--atlstaticregistry"></a><a name="_atl_static_registry"></a>_ATL_STATIC_REGISTRY  
 Ein Symbol, das angibt, dass Sie den Code zur Registrierung für das Objekt in das Objekt, das eine Abhängigkeit von ATL vermeiden möchten DLL.  
  
```
#define _ATL_STATIC_REGISTRY
```  
  
### <a name="remarks"></a>Hinweise  
 Beim definieren **ATL_STATIC_REGISTRY**, sollten Sie den folgenden Code verwenden:  
  
 [!code-cpp[NVC_ATL_EventHandlingSample&5;](../../atl/codesnippet/cpp/registry-macros_1.cpp)]  
  
##  <a name="a-namedeclarelibida--declarelibid"></a><a name="declare_libid"></a>DECLARE_LIBID  
 Bietet eine Möglichkeit für ATL zum Abrufen der *Libid* der Typbibliothek.  
  
```
DECLARE_LIBID( libid )
```  
  
### <a name="parameters"></a>Parameter  
 *LIBID*  
 Die GUID der Typbibliothek.  
  
### <a name="remarks"></a>Hinweise  
 Verwendung `DECLARE_LIBID` in einer `CAtlModuleT`-Klasse.  
  
### <a name="example"></a>Beispiel  
 Vom Assistenten generierte ATL-Projekte nicht attributiert werden ein Beispiel für die Verwendung dieses Makro haben.  
  
##  <a name="a-namedeclarenoregistrya--declarenoregistry"></a><a name="declare_no_registry"></a>DECLARE_NO_REGISTRY  
 Verwendung `DECLARE_NO_REGISTRY` sollten Sie eine standardmäßige ATL-Registrierung für die Klasse zu vermeiden, in denen dieses Makro wird angezeigt.  
  
```
DECLARE_NO_REGISTRY()
```  
  
##  <a name="a-namedeclareregistrya--declareregistry"></a><a name="declare_registry"></a>DECLARE_REGISTRY  
 Gibt die standard-Klasse-Registrierung in der Registrierung oder aus der Registrierung entfernt wird.  
  
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
 [in] Aus Gründen der Abwärtskompatibilität enthalten.  
  
 `pid`  
 [in] Ein `LPCTSTR` , der Bezeichner einer Anwendung hängt von der Version.  
  
 *vpid*  
 [in] Ein `LPCTSTR` , der Bezeichner eine versionsunabhängige Programm.  
  
 *nID*  
 [in] Ein **UINT** also einen Index der Ressourcenzeichenfolge in der Registrierung als die Beschreibung des Programms verwendet.  
  
 `flags`  
 [in] Ein `DWORD` mit dem Programm der threading-Modell in der Registrierung. Muss einer der folgenden Werte sein: **THREADFLAGS_APARTMENT**, **THREADFLAGS_BOTH**, oder **AUTPRXFLAG**.  
  
### <a name="remarks"></a>Hinweise  
 Die standard-Registrierung besteht aus der CLSID Programm-ID, versionsunabhängigen Programm-ID, Beschreibung und Threadmodell.  
  
 Wenn Sie ein Objekt erstellen oder ein Steuerelement mit dem ATL-Klassen-Assistenten, der Assistenten automatisch implementiert die Unterstützung für skriptbasierte Registrierung und fügt die [DECLARE_REGISTRY_RESOURCEID](#declare_registry_resourceid) Makro auf Ihre Dateien. Wenn Sie skriptbasierte Registrierung Unterstützung nicht möchten, müssen Sie dieses Makro mit ersetzen `DECLARE_REGISTRY`. `DECLARE_REGISTRY`Fügt nur die fünf grundlegenden Tasten oben in der Registrierung. Sie müssen manuell Code zum Einfügen der andere Schlüssel in der Registrierung schreiben.  
  
##  <a name="a-namedeclareregistryappidresourceida--declareregistryappidresourceid"></a><a name="declare_registry_appid_resourceid"></a>DECLARE_REGISTRY_APPID_RESOURCEID  
 Gibt an, die Angaben zur automatischen Registrierung der *Appid*.  
  
```
DECLARE_REGISTRY_APPID_RESOURCEID(
    resid, 
    appid )
```  
  
### <a name="parameters"></a>Parameter  
 *RESID*  
 Die Ressourcen-Id der .rgs-Datei enthält Informationen zu den *Appid*.  
  
 *AppID-Element*  
 Ein GUID.  
  
### <a name="remarks"></a>Hinweise  
 Verwendung `DECLARE_REGISTRY_APPID_RESOURCEID` in einer `CAtlModuleT`-Klasse.  
  
### <a name="example"></a>Beispiel  
 Klassen, die ATL-Projekte hinzugefügt, mit dem Assistenten zum Hinzufügen von Klassen von Code sind ein Beispiel für die Verwendung dieses Makro ausgeführt wird.  
  
##  <a name="a-namedeclareregistryresourcea--declareregistryresource"></a><a name="declare_registry_resource"></a>DECLARE_REGISTRY_RESOURCE  
 Ruft die benannte Ressource nicht mit der Registrierungsdatei und führt das Skript aus, um Objekte in der Registrierung eingeben oder aus der Registrierung entfernen.  
  
```
DECLARE_REGISTRY_RESOURCE( x )
```  
  
### <a name="parameters"></a>Parameter  
 *x*  
 [in] Zeichenfolgen Sie-ID der Ressource.  
  
### <a name="remarks"></a>Hinweise  
 Wenn Sie ein Objekt erstellen oder Steuern mit der ATL-Projekt-Assistent, der Assistent automatisch implementieren die Unterstützung für skriptbasierte Registrierung und Hinzufügen der [DECLARE_REGISTRY_RESOURCEID](#declare_registry_resourceid) -Makro, das ähnelt `DECLARE_REGISTRY_RESOURCE`, auf Ihre Dateien.  
  
 Sie können mit der ATL-Registrierungskomponente (Registrar) für den Zugriff auf die optimierte Registrierung statisch verknüpfen. Um mit der Registrierungsstelle Code statisch zu verknüpfen, fügen Sie die folgende Zeile zur Datei "stdafx.h":  
  
 [!code-cpp[NVC_ATL_COM&#56;](../../atl/codesnippet/cpp/registry-macros_2.h)]  
  
 Wenn Sie ATL Ersetzungswerte zur Laufzeit ersetzen möchten, geben Sie die `DECLARE_REGISTRY_RESOURCE` oder `DECLARE_REGISTRY_RESOURCEID` Makro. Erstellen Sie stattdessen ein Array von **_ATL_REGMAP_ENTRIES** Strukturen, in dem jeder Eintrag einen Variable Platzhalter enthält kombiniert mit einem Wert zur Laufzeit den Platzhalter zu ersetzen. Rufen Sie dann [CAtlModule::UpdateRegistryFromResourceD](catlmodule-class.md#updateregistryfromresourced) oder [CAtlModule::UpdateRegistryFromResourceS](catlmodule-class.md#updateregistryfromresources), übergeben Sie das Array. Dadurch werden alle Ersatzwerte in der **_ATL_REGMAP_ENTRIES** Strukturen der Registrierungsstelle Ersatz-Zuordnung.  

  
 Weitere Informationen über ersetzbare Parameter und scripting finden Sie im Artikel [die ATL-Registrierungskomponente (Registrar)](../../atl/atl-registry-component-registrar.md).  
  
##  <a name="a-namedeclareregistryresourceida--declareregistryresourceid"></a><a name="declare_registry_resourceid"></a>DECLARE_REGISTRY_RESOURCEID  
 Identisch mit [DECLARE_REGISTRY_RESOURCE](#declare_registry_resource) , jedoch eine vom Assistenten generierter verwendet **UINT** zum Identifizieren der Ressource, anstatt ein Zeichenfolgenname.  
  
```
DECLARE_REGISTRY_RESOURCEID( x )
```  
  
### <a name="parameters"></a>Parameter  
 *x*  
 [in] Vom Assistenten generierte Bezeichner der Ressource.  
  
### <a name="remarks"></a>Hinweise  
 Beim Erstellen eines Objekts oder Steuern von ATL-Projekt-Assistenten mit der Assistent automatisch implementieren die Unterstützung für skriptbasierte Registrierung und Hinzufügen der `DECLARE_REGISTRY_RESOURCEID` Makro auf Ihre Dateien.  
  
 Sie können mit der ATL-Registrierungskomponente (Registrar) für den Zugriff auf die optimierte Registrierung statisch verknüpfen. Um mit der Registrierungsstelle Code statisch zu verknüpfen, fügen Sie die folgende Zeile zur Datei "stdafx.h":  
  
 [!code-cpp[NVC_ATL_COM&#56;](../../atl/codesnippet/cpp/registry-macros_2.h)]  
  
 Wenn Sie ATL Ersetzungswerte zur Laufzeit ersetzen möchten, geben Sie die `DECLARE_REGISTRY_RESOURCE` oder `DECLARE_REGISTRY_RESOURCEID` Makro. Erstellen Sie stattdessen ein Array von **_ATL_REGMAP_ENTRIES** Strukturen, in dem jeder Eintrag einen Variable Platzhalter enthält kombiniert mit einem Wert zur Laufzeit den Platzhalter zu ersetzen. Rufen Sie dann [CAtlModule::UpdateRegistryFromResourceD](catlmodule-class.md#updateregistryfromresourced) oder [CAtlModule::UpdateRegistryFromResourceS](catlmodule-class.md#updateregistryfromresources), übergeben Sie das Array. Dadurch werden alle Ersatzwerte in der **_ATL_REGMAP_ENTRIES** Strukturen der Registrierungsstelle Ersatz-Zuordnung.  

  
 Weitere Informationen über ersetzbare Parameter und scripting finden Sie im Artikel [die ATL-Registrierungskomponente (Registrar)](../../atl/atl-registry-component-registrar.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Makros](../../atl/reference/atl-macros.md)

