---
title: CComCoClass Klasse | Microsoft-Dokumentation
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 6201051a38ac65788086dcf7ee4c3f3441988e71
ms.lasthandoff: 02/24/2017

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
 Abgeleitet von die Klasse `CComCoClass`.  
  
 *pclsid*  
 Ein Zeiger auf die CLSID des Objekts.  
  
## <a name="members"></a>Mitglieder  
  
### <a name="public-methods"></a>Öffentliche Methoden  
  
|Name|Beschreibung|  
|----------|-----------------|  
|[CComCoClass::CreateInstance](#createinstance)|(Statisch) Erstellt eine Instanz der Klasse und Abfragen für eine Schnittstelle.|  
|[CComCoClass::Error](#error)|(Statisch) Gibt den ausführlichen Fehlerinformationen an den Client zurück.|  
|[CComCoClass::GetObjectCLSID](#getobjectclsid)|(Statisch) Gibt die Klassen-ID des Objekts zurück.|  
|[CComCoClass::GetObjectDescription](#getobjectdescription)|(Statisch) Überschreiben Sie, um die Beschreibung des Objekts zurückzugeben.|  
  
## <a name="remarks"></a>Hinweise  
 `CComCoClass`Stellt Methoden zum Abrufen der CLSID des Objekts, das Festlegen von Fehlerinformationen und Erstellen von Instanzen der Klasse. Jede beliebige Klasse registriert wird, der [objektzuordnung](http://msdn.microsoft.com/en-us/b57619cc-534f-4b8f-bfd4-0c12f937202f) abgeleitet werden soll `CComCoClass`.  
  
 `CComCoClass`definiert auch die Klasse Factory und Aggregation Standardmodell für das Objekt. `CComCoClass`verwendet die folgenden beiden Makros:  
  
- [DECLARE_CLASSFACTORY](http://msdn.microsoft.com/library/51a6b925-07c0-4d3a-9174-0b8c808975e4) deklariert die Klassenfactory sein [CComClassFactory](../../atl/reference/ccomclassfactory-class.md).  
  
- [DECLARE_AGGREGATABLE](http://msdn.microsoft.com/library/e7e568d7-04e0-4226-b5dc-224deed229ab) deklariert, dass das Objekt aggregiert werden kann.  
  
 Sie können diese Standardeinstellungen überschreiben, indem Sie in der Klassendefinition ein anderes Makro angeben. Beispielsweise verwenden Sie [CComClassFactory2](../../atl/reference/ccomclassfactory2-class.md) anstelle von `CComClassFactory`, geben Sie die [DECLARE_CLASSFACTORY2](http://msdn.microsoft.com/library/38a6c969-7297-4bb1-9ba6-1fe2d355b285) Makro:  
  
 [!code-cpp[NVC_ATL_COM&#2;](../../atl/codesnippet/cpp/ccomcoclass-class_1.h)]  
  
## <a name="requirements"></a>Anforderungen  
 **Header:** Standardschnittstellen  
  
##  <a name="createinstance"></a>CComCoClass::CreateInstance  
 Verwenden Sie diese `CreateInstance` Funktionen zum Erstellen einer Instanz einer COM-Objekt und einen Schnittstellenzeiger ohne Verwendung der COM-API abrufen.  
  
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
 [out] Die Adresse einer Zeigervariablen, die den angeforderten Schnittstellenzeiger empfängt, nach erfolgreicher Erstellung.  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert. Finden Sie unter [CoCreateInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615) in der [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] eine Beschreibung der möglichen Rückgabewerte.  
  
### <a name="remarks"></a>Hinweise  
 Verwenden Sie die erste Überladung dieser Funktion zum Erstellen eines normalen Objekts. Verwenden Sie die zweite Überladung, wenn Sie das zu erstellende Objekt aggregieren möchten.  
  
 ATL-Klasse, die die erforderlichen COM-Objekt implementiert (d. h. die Klasse als der erste Vorlagenparameter [CComCoClass](../../atl/reference/ccomcoclass-class.md)) muss im gleichen Projekt wie der aufrufende Code. Die Erstellung des COM-Objekts erfolgt durch die Klassenfactory für diese ATL-Klasse registriert.  
  
 Diese Funktionen sind hilfreich für das Erstellen von Objekten, die Sie, extern erstellt verhindert mithilfe der [OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](http://msdn.microsoft.com/library/abdc093c-6502-42de-8419-b7ebf45299d1) Makro. Sie sind außerdem hilfreich in Situationen, in denen Sie die COM-API aus Gründen der Effizienz zu vermeiden.  
  
 Beachten Sie, dass die Schnittstelle `Q` benötigen Sie eine IID zugeordnet, die mit abgerufen werden kann die [__uuidof](../../cpp/uuidof-operator.md) Operator.  
  
### <a name="example"></a>Beispiel  
 Im folgenden Beispiel `CDocument` ist eine vom Assistenten generierte ATL abgeleitete Klasse `CComCoClass` , implementiert der **IDocument** Schnittstelle. Die Klasse wird registriert, in der objektzuordnung mit dem `OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO` bearbeiten, damit Instanzen des Dokuments mithilfe von Clients erstellt werden können [CoCreateInstance](http://msdn.microsoft.com/library/windows/desktop/ms686615). `CApplication`ist eine Co-Klasse, die eine Methode auf einer eigenen COM-Schnittstellen zum Erstellen von Instanzen der Document-Klasse bereitstellt. Der folgende Code zeigt, wie einfach es zum Erstellen von Instanzen des Dokuments Klasse mithilfe der `CreateInstance` Element geerbt wird, von der `CComCoClass` Basisklasse.  
  
 [!code-cpp[NVC_ATL_COM&#11;](../../atl/codesnippet/cpp/ccomcoclass-class_2.cpp)]  
  
##  <a name="error"></a>CComCoClass::Error  
 Diese statischen Funktion richtet die `IErrorInfo` Schnittstelle Fehlerinformationen an den Client bereitstellen.  
  
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
 [in] Die Zeichenfolge, die den Fehler beschreibt. Der Unicode-Version `Error` gibt an, dass `lpszDesc` ist vom Typ **LPCOLESTR**; die ANSI-Version gibt den Typ des `LPCSTR`.  
  
 `iid`  
 [in] Die IID für die Schnittstelle, die den Fehler definieren oder `GUID_NULL` (Standardwert), wenn der Fehler vom Betriebssystem definiert ist.  
  
 `hRes`  
 [in] Die `HRESULT` an den Aufrufer zurückgegeben werden sollen. Der Standardwert ist 0. Weitere Informationen über `hRes`, finden Sie unter "Hinweise".  
  
 `nID`  
 [in] Der Ressourcenbezeichner, wo die Fehlerbeschreibungszeichenfolge gespeichert werden. Dieser Wert sollte zwischen 0 x 0200 und 0xFFFF liegen. In Debugbuilds eine **ASSERT** führt, wenn `nID` nicht indizieren, eine gültige Zeichenfolge. In Releasebuilds wird die Zeichenfolge zur fehlerbeschreibung festgelegt auf "Ein Fehler aufgetreten."  
  
 `dwHelpID`  
 [in] Den Hilfekontextbezeichner für den Fehler.  
  
 `lpszHelpFile`  
 [in] Der Pfad und Name der Hilfedatei, die den Fehler beschreibt.  
  
 `hInst`  
 [in] Das Handle für die Ressource. Dieser Parameter ist standardmäßig **_AtlModule::GetResourceInstance**, wobei **_AtlModule** ist die globale Instanz von [von CAtlModule](../../atl/reference/catlmodule-class.md).  
  
### <a name="return-value"></a>Rückgabewert  
 Ein Standard `HRESULT` -Wert. Einzelheiten finden Sie unter "Hinweise".  
  
### <a name="remarks"></a>Hinweise  
 Aufrufen `Error`, muss Ihr Objekt implementiert die `ISupportErrorInfo Interface` Schnittstelle.  
  
 Wenn die `hRes` Parameter ist ein Wert ungleich NULL `Error` gibt den Wert der `hRes`. Wenn `hRes` ist&0; (null), und klicken Sie dann auf die ersten vier Versionen von `Error` zurückgeben `DISP_E_EXCEPTION`. Die letzten beiden Versionen zurück, das Ergebnis des Makros **MAKE_HRESULT (1, FACILITY_ITF,** `nID` **)**.  
  
##  <a name="getobjectclsid"></a>CComCoClass::GetObjectCLSID  
 Bietet eine einheitliche Methode zum Abrufen der CLSID des Objekts.  
  
```
static const CLSID& WINAPI GetObjectCLSID();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Klassen-ID des Objekts.  
  
##  <a name="getobjectdescription"></a>CComCoClass::GetObjectDescription  
 Die statische Funktion ruft die Beschreibung für das Klassenobjekt ab.  
  
```
static LPCTSTR WINAPI GetObjectDescription();
```  
  
### <a name="return-value"></a>Rückgabewert  
 Beschreibung für das Klassenobjekt.  
  
### <a name="remarks"></a>Hinweise  
 Die standardmäßige Implementierung gibt **NULL**. Sie können diese Methode mit überschreiben die [DECLARE_OBJECT_DESCRIPTION](http://msdn.microsoft.com/library/32ac881c-97b1-44e2-a017-0e23eb99ac93) Makro. Zum Beispiel:  
  
 [!code-cpp[NVC_ATL_COM&#12;](../../atl/codesnippet/cpp/ccomcoclass-class_3.h)]  
  
 `GetObjectDescription`wird aufgerufen, indem **IComponentRegistrar::GetComponents**. **IComponentRegistrar** ist eine Automatisierungsschnittstelle, mit der Sie an-und Abmelden einzelne Komponenten in einer DLL. Wenn Sie ein Objekt für die Registrierung der Komponente mit dem Assistenten für ATL-Projekt erstellen, wird automatisch der Assistent implementiert die **IComponentRegistrar** Schnittstelle. **IComponentRegistrar** wird normalerweise von Microsoft Transaction Server verwendet.  
  
 Weitere Informationen über ATL-Projekt-Assistenten finden Sie im Artikel [Erstellen eines ATL-Projekts](../../atl/reference/creating-an-atl-project.md).  
  
## <a name="see-also"></a>Siehe auch  
 [Übersicht über die Klasse](../../atl/atl-class-overview.md)

