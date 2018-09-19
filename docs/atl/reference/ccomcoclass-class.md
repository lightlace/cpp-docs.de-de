---
title: CComCoClass-Klasse | Microsoft-Dokumentation
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 11c391e6ad467c835cd8c65ec872db74b85404a2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2018
ms.locfileid: "46097613"
---
# <a name="ccomcoclass-class"></a>CComCoClass-Klasse

Diese Klasse stellt Methoden zum Erstellen von Instanzen einer Klasse und ihre Eigenschaften abrufen.

## <a name="syntax"></a>Syntax

```
template <class T, const CLSID* pclsid = &CLSID_NULL>
class CComCoClass
```

#### <a name="parameters"></a>Parameter

*T*<br/>
Abgeleitet von die Klasse `CComCoClass`.

*pclsid*<br/>
Ein Zeiger auf die CLSID des Objekts.

## <a name="members"></a>Member

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung|
|----------|-----------------|
|[CComCoClass::CreateInstance](#createinstance)|(Statisch) Erstellt eine Instanz der Klasse und Abfragen für eine Schnittstelle.|
|[CComCoClass::Error](#error)|(Statisch) Ausführliche Fehlerinformationen zurück an den Client.|
|[CComCoClass::GetObjectCLSID](#getobjectclsid)|(Statisch) Gibt die Klassenbezeichner des Objekts zurück.|
|[CComCoClass::GetObjectDescription](#getobjectdescription)|(Statisch) Überschreiben Sie, um die Beschreibung des Objekts zurück.|

## <a name="remarks"></a>Hinweise

`CComCoClass` Stellt Methoden zum Abrufen von CLSID des Objekts, das Festlegen von Fehlerinformationen und Erstellen von Instanzen der Klasse. Jede Klasse, die in der objektzuordnung registriert abgeleitet werden sollte `CComCoClass`.

`CComCoClass` definiert außerdem das Klasse Factory und Aggregation Standardmodell für Ihr Objekt aus. `CComCoClass` verwendet die folgenden beiden Makros:

- [DECLARE_CLASSFACTORY](aggregation-and-class-factory-macros.md#declare_classfactory) deklariert die Klassenfactory sein [CComClassFactory](../../atl/reference/ccomclassfactory-class.md).

- [DECLARE_AGGREGATABLE](aggregation-and-class-factory-macros.md#declare_aggregatable) deklariert, dass das Objekt aggregiert werden kann.

Sie können diese Standardeinstellungen überschreiben, indem Sie ein anderes Makro in der Klassendefinition angeben. Um beispielsweise verwenden [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md) anstelle von `CComClassFactory`, geben Sie die [DECLARE_CLASSFACTORY2](aggregation-and-class-factory-macros.md#declare_classfactory2) Makro:

[!code-cpp[NVC_ATL_COM#2](../../atl/codesnippet/cpp/ccomcoclass-class_1.h)]

## <a name="requirements"></a>Anforderungen

**Header:** atlcom.h

##  <a name="createinstance"></a>  CComCoClass::CreateInstance

Verwenden Sie diese `CreateInstance` Funktionen zum Erstellen einer Instanz einer COM-Objekt, und einen Schnittstellenzeiger ohne Verwendung der COM-API abrufen.

```
template <class  Q>
static HRESULT CreateInstance( Q** pp);

template <class  Q>
static HRESULT CreateInstance(IUnknown* punkOuter, Q** pp);
```

### <a name="parameters"></a>Parameter

*Q*<br/>
Die COM-Schnittstelle, die über zurückgegeben werden sollen *pp*.

*punkOuter*<br/>
[in] Die äußere unbekannte oder "Unbekannt" des Aggregats steuern.

*PP*<br/>
[out] Die Adresse einer Zeigervariablen, die den angeforderten Schnittstellenzeiger empfängt, wenn Erstellung erfolgreich ist.

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert. Finden Sie unter [CoCreateInstance](/windows/desktop/api/combaseapi/nf-combaseapi-cocreateinstance) im Windows SDK für eine Beschreibung der möglichen Rückgabewerte.

### <a name="remarks"></a>Hinweise

Verwenden Sie die erste Überladung dieser Funktion für die typische objekterstellung; Verwenden Sie die zweite Überladung, wenn Sie das zu erstellende Objekt aggregieren möchten.

Der ATL-Klasse implementiert die erforderlichen COM-Objekt (d. h. die Klasse, die als der erste Vorlagenparameter verwendet [CComCoClass](../../atl/reference/ccomcoclass-class.md)) muss sich im gleichen Projekt wie der aufrufende Code. Die Erstellung von COM-Objekts wird durch die Klassenfactory für diese ATL-Klasse registriert ausgeführt.

Diese Funktionen sind hilfreich zum Erstellen von Objekten, das Sie extern erstellt wird, mit verhindert die [OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](object-map-macros.md#object_entry_non_createable_ex_auto) Makro. Sie sind auch hilfreich in Situationen, in dem Sie die COM-API aus Gründen der Effizienz zu vermeiden möchten.

Beachten Sie, dass die Schnittstelle *Q* benötigen eine IID zugeordnet, die mit abgerufen werden kann die [__uuidof](../../cpp/uuidof-operator.md) Operator.

### <a name="example"></a>Beispiel

Im folgenden Beispiel `CDocument` ist eine vom Assistenten generierte ATL abgeleitete Klasse `CComCoClass` , implementiert die `IDocument` Schnittstelle. Die Klasse wird in der objektzuordnung mit dem Makro OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO registriert, damit Instanzen des Dokuments mithilfe von Clients erstellt werden können [CoCreateInstance](/windows/desktop/api/combaseapi/nf-combaseapi-cocreateinstance). `CApplication` ist eine Co-Klasse, die eine Methode auf einem der eigenen COM-Schnittstellen zum Erstellen von Instanzen der Document-Klasse bereitstellt. Der folgende Code zeigt, wie einfach es zum Erstellen von Instanzen der Klasse für das Dokument mit den `CreateInstance` Member geerbt von der `CComCoClass` Basisklasse.

[!code-cpp[NVC_ATL_COM#11](../../atl/codesnippet/cpp/ccomcoclass-class_2.cpp)]

##  <a name="error"></a>  CComCoClass::Error

Diese statischen Funktion richtet die `IErrorInfo` Schnittstelle, um Fehlerinformationen an den Client bereitzustellen.

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

*lpszDesc*<br/>
[in] Die Zeichenfolge, die den Fehler beschreibt. Die Unicode-Version von `Error` gibt an, dass *LpszDesc* vom LPCOLESTR geben an, die ANSI-Version gibt eine Art von LPCSTR.

*IID*<br/>
[in] Die IID der Schnittstelle definieren den Fehler oder die GUID_NULL (Standardwert), wenn der Fehler vom Betriebssystem definiert ist.

*' hres '*<br/>
[in] Das HRESULT, Sie möchten, die an den Aufrufer zurückgegeben werden. Der Standardwert ist 0. Weitere Informationen zu *' hres '*, finden Sie unter "Hinweise".

*nID*<br/>
[in] Der Ressourcenbezeichner, in dem die Zeichenfolge zur fehlerbeschreibung gespeichert ist. Dieser Wert sollte zwischen 0 x 0200 und 0xFFFF liegen. In Debugbuilds einer **ASSERT** führt, wenn *nID* indiziert sich nicht auf eine gültige Zeichenfolge. In Releasebuilds wird die Zeichenfolge zur fehlerbeschreibung festgelegt, "Unbekannter Fehler."

*dwHelpID*<br/>
[in] Den Hilfekontextbezeichner für den Fehler.

*lpszHelpFile*<br/>
[in] Der Pfad und Name der Hilfedatei, die den Fehler beschreibt.

*hInst*<br/>
[in] Das Handle für die Ressource. Standardmäßig ist dieser Parameter `_AtlModule::GetResourceInstance`, wobei `_AtlModule` ist die globale Instanz des [CAtlModule](../../atl/reference/catlmodule-class.md).

### <a name="return-value"></a>Rückgabewert

Ein standard HRESULT-Wert. Einzelheiten finden Sie unter "Hinweise".

### <a name="remarks"></a>Hinweise

Aufzurufende `Error`, muss Ihr Objekt implementieren die `ISupportErrorInfo Interface` Schnittstelle.

Wenn die *' hres '* Parameter ungleich NULL ist, klicken Sie dann `Error` gibt den Wert der *' hres '*. Wenn *' hres '* ist 0 (null), und klicken Sie dann auf die ersten vier Versionen von `Error` DISP_E_EXCEPTION zurück. Die letzten beiden Versionen Zurückgeben des Ergebnisses des Makros **MAKE_HRESULT (1, FACILITY_ITF,** *nID* **)**.

##  <a name="getobjectclsid"></a>  CComCoClass::GetObjectCLSID

Bietet eine einheitliche Möglichkeit zum Abrufen der CLSID des Objekts.

```
static const CLSID& WINAPI GetObjectCLSID();
```

### <a name="return-value"></a>Rückgabewert

Klassen-ID des Objekts.

##  <a name="getobjectdescription"></a>  CComCoClass::GetObjectDescription

Diese statischen Funktion ruft die textbeschreibung für das Klassenobjekt ab.

```
static LPCTSTR WINAPI GetObjectDescription();
```

### <a name="return-value"></a>Rückgabewert

Die Klasse die Beschreibung des Objekts.

### <a name="remarks"></a>Hinweise

Die Standardimplementierung gibt NULL zurück. Sie können angeben, überschreiben diese Methode mit dem [DECLARE_OBJECT_DESCRIPTION](object-map-macros.md#declare_object_description) Makro. Zum Beispiel:

[!code-cpp[NVC_ATL_COM#12](../../atl/codesnippet/cpp/ccomcoclass-class_3.h)]

`GetObjectDescription` wird aufgerufen, indem `IComponentRegistrar::GetComponents`. `IComponentRegistrar` ist eine Automatisierungsschnittstelle, mit dem Sie an-und Abmelden einzelne Komponenten in einer DLL. Wenn Sie ein Objekt für die Registrierung der Komponente mit dem ATL-Projekt-Assistenten erstellen, wird der Assistent automatisch implementieren die `IComponentRegistrar` Schnittstelle. `IComponentRegistrar` von Microsoft Transaction Server ist in der Regel verwendet werden.

Weitere Informationen über ATL-Projektassistenten finden Sie im Artikel [Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md).

## <a name="see-also"></a>Siehe auch

[Übersicht über die Klasse](../../atl/atl-class-overview.md)
