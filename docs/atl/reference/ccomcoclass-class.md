---
title: CComCoClass Klasse | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComCoClass
- ATLCOM/ATL::CComCoClass
- ATLCOM/ATL::CComCoClass::CreateInstance
- ATLCOM/ATL::CComCoClass::Error
- ATLCOM/ATL::CComCoClass::GetObjectCLSID
- ATLCOM/ATL::CComCoClass::GetObjectDescription
dev_langs:
- C++
helpviewer_keywords:
- CComCoClass class
- aggregation [C++], aggregation models
ms.assetid: 67cfefa4-8df9-47fa-ad58-2d1a1ae25762
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 969370294ed3d5d2ca2fdff5f4a106b72ed77a17
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2017
---
# <a name="ccomcoclass-class"></a>CComCoClass-Klasse
Diese Klasse stellt Methoden zum Erstellen von Instanzen einer Klasse und ihre Eigenschaften abrufen.  
  
## <a name="syntax"></a>Syntax  
  
```
template <class T, const CLSID* pclsid = &CLSID_NULL>  
class CComCoClass
```  
  
#### <a name="parameters"></a>Parameter  
 `T`  
 Die Klasse abgeleitet `CComCoClass`.  
  
 *pclsid*  
 Ein Zeiger auf die CLSID des Objekts.  
  
## <a name="members"></a>Member  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComCoClass::CreateInstance](#createinstance)|(Statisch) Erstellt eine Instanz der Klasse und Abfragen für eine Schnittstelle.|  
|[CComCoClass::Error](#error)|(Statisch) Ausführliche Fehlerinformationen zurückgegeben an den Client.|  
|[CComCoClass::GetObjectCLSID](#getobjectclsid)|(Statisch) Gibt die Klassenbezeichner des Objekts zurück.|  
|[CComCoClass::GetObjectDescription](#getobjectdescription)|(Statisch) Außer Kraft setzen Sie, um die Beschreibung des Objekts zurückzugeben.|  
  
## <a name="remarks"></a>Hinweise  
 `CComCoClass`Stellt Methoden zum Abrufen von CLSID für ein Objekt, das Fehlerinformationen festlegen und das Erstellen von Instanzen der Klasse bereit. Jede Klasse registriert wird, der [objektzuordnung](http://msdn.microsoft.com/en-us/b57619cc-534f-4b8f-bfd4-0c12f937202f) abgeleitet werden sollte `CComCoClass`.  
  
 `CComCoClass`definiert auch die Klasse Factory und Aggregation Standardmodell für Ihr Objekt. `CComCoClass`verwendet die folgenden beiden Makros:  
  
- [DECLARE_CLASSFACTORY](aggregation-and-class-factory-macros.md#declare_classfactory) deklariert die Klassenfactory sein [CComClassFactory](../../atl/reference/ccomclassfactory-class.md).  
  
- [DECLARE_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_aggregatable) deklariert, dass das Objekt aggregiert werden kann.  
  
 Sie können diese Standardeinstellungen überschreiben, indem Sie ein anderes Makro in der Klasse angeben. Beispielsweise verwenden [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md) anstelle von `CComClassFactory`, geben Sie die [DECLARE_CLASSFACTORY2](aggregation-and-class-factory-macros.md#declare_classfactory2) Makro:  
  
 [!code-cpp[NVC_ATL_COM#2](../../atl/codesnippet/cpp/ccomcoclass-class_1.h)]  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** atlcom.h  
  
##  <a name="createinstance"></a>CComCoClass::CreateInstance  
 Verwenden Sie diese `CreateInstance` Funktionen zum Erstellen einer Instanz einer COM-Objekt und einen Schnittstellenzeiger abzurufen, ohne Verwendung der COM-API.  
  
```
template <class  Q>
static HRESULT CreateInstance( Q** pp);

template <class  Q>
static HRESULT CreateInstance(IUnknown* punkOuter, Q** pp);
```  
  
### <a name="parameters"></a>Parameter  
 `Q`  
 Die COM-Schnittstelle, die über zurückgegeben werden sollen `pp`.  
  
 *punkOuter*  
 [in] Die äußere unbekannte oder "Unbekannt" Steuern des Aggregats.  
  
 `pp`  
 [out] Die Adresse einer Zeigervariablen, die den angeforderten Schnittstellenzeiger empfängt, bei erfolgreicher Erstellung.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert. Finden Sie unter [CoCreateInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615) in das Windows SDK für eine Beschreibung der möglichen Rückgabewerte.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie die erste Überladung dieser Funktion für die typische objekterstellung; Verwenden Sie die zweite Überladung, wenn Sie benötigen, um das zu erstellende Objekt zu aggregieren.  
  
 ATL-Klasse, die das erforderliche COM-Objekt implementiert (d. h. der Klasse, die verwendet wird, als der erste Vorlagenparameter [CComCoClass](../../atl/reference/ccomcoclass-class.md)) muss sich im gleichen Projekt wie der aufrufende Code. Die Erstellung des COM-Objekts erfolgt durch die Klassenfactory für diese Klasse ATL registriert.  
  
 Diese Funktionen sind hilfreich zum Erstellen von Objekten, die Sie, extern erstellbar verhindert mithilfe der [OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](object-map-macros.md#object_entry_non_createable_ex_auto) Makro. Sie sind auch hilfreich in Situationen, in dem Sie die COM-API aus Gründen der Effizienz zu vermeiden möchten.  
  
 Beachten Sie, dass die Schnittstelle `Q` benötigen eine IID zugeordnet, die mit abgerufen werden kann die [__uuidof](../../cpp/uuidof-operator.md) Operator.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel `CDocument` ist eine vom Assistenten generierten ATL abgeleitete Klasse `CComCoClass` , implementiert die **IDocument** Schnittstelle. Die Klasse wird in der objektzuordnung mit registriert die `OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO` Makros, damit Instanzen des Dokuments mithilfe von Clients erstellt werden können [CoCreateInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615). `CApplication`ist eine Co-Klasse, die eine Methode auf einem eigenen COM-Schnittstellen zum Erstellen von Instanzen der Dokumentklasse bereitstellt. Der folgende Code zeigt, wie einfach es zum Erstellen von Instanzen der Klasse für das Dokument mit der `CreateInstance` Element geerbt wird, von der `CComCoClass` Basisklasse.  
  
 [!code-cpp[NVC_ATL_COM#11](../../atl/codesnippet/cpp/ccomcoclass-class_2.cpp)]  
  
##  <a name="error"></a>CComCoClass::Error  
 Diese statische Funktion richtet die `IErrorInfo` Schnittstelle, um Informationen an den Client zu senden.  
  
```
static HRESULT WINAPI Error(
    LPCOLESTR lpszDesc,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0);

static HRESULT WINAPI Error(
    LPCOLESTR lpszDesc,
    DWORD dwHelpID,
    LPCOLESTR lpszHelpFile,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0);

static HRESULT WINAPI Error(
    LPCSTR lpszDesc,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0);

static HRESULT WINAPI Error(
    LPCSTR lpszDesc,
    DWORD dwHelpID,
    LPCSTR lpszHelpFile,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0);

static HRESULT WINAPI Error(
    UINT nID,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0,
    HINSTANCE hInst = _AtlBaseModule.GetResourceInstance ());

static HRESULT Error(
    UINT nID,
    DWORD dwHelpID,
    LPCOLESTR lpszHelpFile,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0,
    HINSTANCE hInst = _AtlBaseModule.GetResourceInstance());
```  
  
### <a name="parameters"></a>Parameter  
 `lpszDesc`  
 [in] Die Zeichenfolge, die den Fehler beschreibt. Die Unicode-Version des `Error` gibt an, dass `lpszDesc` ist vom Typ **LPCOLESTR**; die ANSI-Version gibt den Typ des `LPCSTR`.  
  
 `iid`  
 [in] Die IID der Schnittstelle, die den Fehler definieren oder `GUID_NULL` (Standardwert), wenn der Fehler vom Betriebssystem definiert ist.  
  
 `hRes`  
 [in] Die `HRESULT` an den Aufrufer zurückgegeben werden sollen. Der Standardwert ist 0. Weitere Informationen zu `hRes`, finden Sie unter "Hinweise".  
  
 `nID`  
 [in] Der Ressourcenbezeichner, in dem die Zeichenfolge zur fehlerbeschreibung gespeichert ist. Dieser Wert sollte zwischen 0 x 0200 und 0xFFFF liegen. Debug-Builds ein **ASSERT** führt `nID` eine gültige Zeichenfolge keinen index erstellt. In Releasebuilds wird die Zeichenfolge zur fehlerbeschreibung auf "Unbekannter Fehler" festgelegt werden  
  
 `dwHelpID`  
 [in] Den Hilfekontextbezeichner für den Fehler.  
  
 `lpszHelpFile`  
 [in] Der Pfad und Name der Hilfedatei, die den Fehler beschreibt.  
  
 `hInst`  
 [in] Das Handle für die Ressource. Standardmäßig ist dieser Parameter **_AtlModule::GetResourceInstance**, wobei **_AtlModule** wird die globale Instanz von [von CAtlModule](../../atl/reference/catlmodule-class.md).  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert. Einzelheiten finden Sie unter "Hinweise".  
  
### <a name="remarks"></a>Hinweise  
 Aufzurufende `Error`, muss Ihr Objekt implementiert die `ISupportErrorInfo Interface` Schnittstelle.  
  
 Wenn die `hRes` -Parameter ist ungleich NULL ist, klicken Sie dann `Error` gibt den Wert der `hRes`. Wenn `hRes` ist 0 (null), und klicken Sie dann auf die ersten vier Versionen des `Error` zurückgeben `DISP_E_EXCEPTION`. Die letzten beiden Versionen zurück, das Ergebnis des Makros **MAKE_HRESULT (1, FACILITY_ITF,** `nID` **)**.  
  
##  <a name="getobjectclsid"></a>CComCoClass::GetObjectCLSID  
 Bietet eine einheitliche Methode zum Abrufen von CLSID des Objekts an.  
  
```
static const CLSID& WINAPI GetObjectCLSID();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Klassen-ID des Objekts.  
  
##  <a name="getobjectdescription"></a>CComCoClass::GetObjectDescription  
 Diese statische Funktion ruft die textbeschreibung für Ihr Klassenobjekt ab.  
  
```
static LPCTSTR WINAPI GetObjectDescription();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Beschreibung für das Klassenobjekt.  
  
### <a name="remarks"></a>Hinweise  
 Gibt die standardmäßige Implementierung **NULL**. Sie können angeben, überschreiben diese Methode mit dem [DECLARE_OBJECT_DESCRIPTION](object-map-macros.md#declare_object_description) Makro. Zum Beispiel:  
  
 [!code-cpp[NVC_ATL_COM#12](../../atl/codesnippet/cpp/ccomcoclass-class_3.h)]  
  
 `GetObjectDescription`wird aufgerufen, indem **IComponentRegistrar::GetComponents**. **IComponentRegistrar** ist eine Automatisierungsschnittstelle, mit der Sie beim Registrieren und Aufheben der einzelne Komponenten in einer DLL. Wenn Sie eine Komponente Registrierungsstelle-Objekt mit dem ATL-Projekt-Assistenten erstellen, wird der Assistent automatisch implementieren die **IComponentRegistrar** Schnittstelle. **IComponentRegistrar** wird meist von Microsoft Transaction Server verwendet.  
  
 Weitere Informationen über ATL-Projektassistenten finden Sie im Artikel [Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Klassenübersicht](../../atl/atl-class-overview.md)
