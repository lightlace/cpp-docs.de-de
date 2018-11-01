---
title: FtmBase-Klasse
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- ftm/Microsoft::WRL::FtmBase
- ftm/Microsoft::WRL::FtmBaseCreateGlobalInterfaceTable
- ftm/Microsoft::WRL::FtmBase::DisconnectObject
- ftm/Microsoft::WRL::FtmBase::FtmBase
- ftm/Microsoft::WRL::FtmBase::GetMarshalSizeMax
- ftm/Microsoft::WRL::FtmBase::GetUnmarshalClass
- ftm/Microsoft::WRL::FtmBase::MarshalInterface
- ftm/Microsoft::WRL::FtmBase::marshaller_
- ftm/Microsoft::WRL::FtmBase::ReleaseMarshalData
- ftm/Microsoft::WRL::FtmBase::UnmarshalInterface
helpviewer_keywords:
- Microsoft::WRL::FtmBase class
- Microsoft::WRL::FtmBase::CreateGlobalInterfaceTable method
- Microsoft::WRL::FtmBase::DisconnectObject method
- Microsoft::WRL::FtmBase::FtmBase, constructor
- Microsoft::WRL::FtmBase::GetMarshalSizeMax method
- Microsoft::WRL::FtmBase::GetUnmarshalClass method
- Microsoft::WRL::FtmBase::MarshalInterface method
- Microsoft::WRL::FtmBase::marshaller_ data member
- Microsoft::WRL::FtmBase::ReleaseMarshalData method
- Microsoft::WRL::FtmBase::UnmarshalInterface method
ms.assetid: 275f3b71-2975-4f92-89e7-d351e96496df
ms.openlocfilehash: fb7f103d8ea647f554d9bbf26c2e218d34f6b1ff
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50431849"
---
# <a name="ftmbase-class"></a>FtmBase-Klasse

Stellt ein Freethread-Marshaller-Objekt dar.

## <a name="syntax"></a>Syntax

```cpp
class FtmBase :
    public Microsoft::WRL::Implements<
        Microsoft::WRL::RuntimeClassFlags<WinRtClassicComMix>,
        Microsoft::WRL::CloakedIid<IMarshal>
    >;
```

## <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter [RuntimeClass-Klasse](runtimeclass-class.md).

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

| Name                         | Beschreibung                                        |
| ---------------------------- | -------------------------------------------------- |
| [Ftmbase:: Ftmbase](#ftmbase) | Initialisiert eine neue Instanz der `FtmBase`-Klasse. |

### <a name="public-methods"></a>Öffentliche Methoden

| Name                                                               | Beschreibung                                                                                                                                                          |
| ------------------------------------------------------------------ | -------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| [Ftmbase:: Createglobalinterfacetable](#createglobalinterfacetable) | Erstellt eine globale Schnittstellentabelle (GIT).                                                                                                                              |
| [Ftmbase:: DisconnectObject](#disconnectobject)                     | Zwangsweise veröffentlicht alle externe Verbindungen zu einem Objekt. Das Objekt der Server Ruft die Implementierung dieser Methode vor dem Herunterfahren des Objekts.                |
| [Ftmbase:: GetMarshalSizeMax](#getmarshalsizemax)                   | Rufen Sie die obere Grenze für die Anzahl von Bytes erforderlich, um den angegebenen Schnittstellenzeiger für das angegebene Objekt gemarshallt werden soll.                                                |
| [Ftmbase:: GetUnmarshalClass](#getunmarshalclass)                   | Ruft die CLSID, die COM verwendet, um die DLL, die den Code für den entsprechenden Proxy zu suchen. COM lädt diese DLL-Datei um eine nicht initialisierte Instanz des Proxys zu erstellen. |
| [Ftmbase:: MarshalInterface](#marshalinterface)                     | Schreibt in einen Stream der Daten, die erforderlich sind, um eine Proxy-Objekt in einem Clientprozess zu initialisieren.                                                                          |
| [Ftmbase:: ReleaseMarshalData](#releasemarshaldata)                 | Zerstört ein gemarshalltes Datenpaket.                                                                                                                                    |
| [Ftmbase::: UnmarshalInterface](#unmarshalinterface)                 | Initialisiert einen neu erstellten Proxy, und gibt einen Schnittstellenzeiger zurück, auf diesen Proxy.                                                                                    |

### <a name="public-data-members"></a>Öffentliche Datenmember

| Name                                | Beschreibung                                       |
| ----------------------------------- | ------------------------------------------------- |
| [Ftmbase:: Marshaller_](#marshaller) | Enthält einen Verweis auf die freethreaded Marshaller. |

## <a name="inheritance-hierarchy"></a>Vererbungshierarchie

`FtmBase`

## <a name="requirements"></a>Anforderungen

**Header:** ftm.h

**Namespace:** Microsoft::WRL

## <a name="createglobalinterfacetable"></a>Ftmbase:: Createglobalinterfacetable

Erstellt eine globale Schnittstellentabelle (GIT).

```cpp
static HRESULT CreateGlobalInterfaceTable(
   __out IGlobalInterfaceTable **git
);
```

### <a name="parameters"></a>Parameter

*Git*<br/>
Wenn dieser Vorgang abgeschlossen ist, einen Zeiger auf eine globale Schnittstellentabelle.

### <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls ein HRESULT, das den Fehler angibt.

### <a name="remarks"></a>Hinweise

Weitere Informationen finden Sie unter den `IGlobalInterfaceTable` Thema in der `COM Interfaces` Unterthema der `COM Reference` in der MSDN Library.

## <a name="disconnectobject"></a>Ftmbase:: DisconnectObject

Zwangsweise veröffentlicht alle externe Verbindungen zu einem Objekt. Das Objekt der Server Ruft die Implementierung dieser Methode vor dem Herunterfahren des Objekts.

```cpp
STDMETHODIMP DisconnectObject(
   __in DWORD dwReserved
) override;
```

### <a name="parameters"></a>Parameter

*dwReserved*<br/>
Für die zukünftige Verwendung reserviert. Muss 0 (null) sein.

### <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls ein HRESULT, das den Fehler angibt.

## <a name="ftmbase"></a>Ftmbase:: Ftmbase

Initialisiert eine neue Instanz der `FtmBase`-Klasse.

```cpp
FtmBase();
```

## <a name="getmarshalsizemax"></a>Ftmbase:: GetMarshalSizeMax

Rufen Sie die obere Grenze für die Anzahl von Bytes erforderlich, um den angegebenen Schnittstellenzeiger für das angegebene Objekt gemarshallt werden soll.

```cpp
STDMETHODIMP GetMarshalSizeMax(
   __in REFIID riid,
   __in_opt void *pv,
   __in DWORD dwDestContext,
   __reserved void *pvDestContext,
   __in DWORD mshlflags,
   __out DWORD *pSize
) override;
```

### <a name="parameters"></a>Parameter

*riid*<br/>
Verweis auf den Bezeichner der Schnittstelle, die gemarshallt werden soll.

*PV*<br/>
Der Schnittstellenzeiger, gemarshallt werden soll; NULL kann sein.

*dwDestContext*<br/>
Zielkontext, in dem die angegebene Schnittstelle zum Marshalling rückgängig gemacht werden wird.

Geben Sie einen oder mehrere MSHCTX-Enumerationswerte.

Rückgängigmachen des Marshallens kann derzeit, die entweder in ein anderes Apartment des aktuellen Prozesses (MSHCTX_INPROC) oder in einem anderen Prozess auf dem gleichen Computer wie der aktuelle Prozess (MSHCTX_LOCAL) auftreten.

*pvDestContext*<br/>
Für die zukünftige Verwendung reserviert. NULL muss sein.

*mshlflags*<br/>
Flag, das angibt, ob die Daten gemarshallt werden zurück an den Clientprozess übertragen werden – der Normalfall – oder in einer globalen Tabelle, in dem sie, indem mehrere Clients abgerufen werden geschrieben. Geben Sie einen oder mehrere MSHLFLAGS-Enumerationswerte.

*pSize*<br/>
Wenn dieser Vorgang abgeschlossen ist, Zeiger auf die obere Grenze für die Menge der Daten in den Marshalling Stream geschrieben werden.

### <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls E_FAIL oder E_NOINTERFACE an.

## <a name="getunmarshalclass"></a>Ftmbase:: GetUnmarshalClass

Ruft die CLSID, die COM verwendet, um die DLL, die den Code für den entsprechenden Proxy zu suchen. COM lädt diese DLL-Datei um eine nicht initialisierte Instanz des Proxys zu erstellen.

```cpp
STDMETHODIMP GetUnmarshalClass(
   __in REFIID riid,
   __in_opt void *pv,
   __in DWORD dwDestContext,
   __reserved void *pvDestContext,
   __in DWORD mshlflags,
   __out CLSID *pCid
) override;
```

### <a name="parameters"></a>Parameter

*riid*<br/>
Verweis auf den Bezeichner der Schnittstelle, die gemarshallt werden soll.

*PV*<br/>
Zeiger auf die Schnittstelle, die gemarshallt werden; Wenn der Aufrufer nicht über einen Zeiger auf die gewünschte Schnittstelle verfügt, kann NULL sein.

*dwDestContext*<br/>
Zielkontext, in dem die angegebene Schnittstelle zum Marshalling rückgängig gemacht werden wird.

Geben Sie einen oder mehrere MSHCTX-Enumerationswerte.

Rückgängigmachen des Marshallens kann entweder in ein anderes Apartment des aktuellen Prozesses (MSHCTX_INPROC) oder in einem anderen Prozess auf dem gleichen Computer wie der aktuelle Prozess (MSHCTX_LOCAL) auftreten.

*pvDestContext*<br/>
Für die zukünftige Verwendung reserviert. NULL muss sein.

*mshlflags*<br/>
Wenn dieser Vorgang abgeschlossen ist, Zeiger auf die CLSID zum Erstellen eines Proxys im Clientprozess verwendet werden.

*pCid*

### <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls S_FALSE.

## <a name="marshalinterface"></a>Ftmbase:: MarshalInterface

Schreibt in einen Stream der Daten, die erforderlich sind, um eine Proxy-Objekt in einem Clientprozess zu initialisieren.

```cpp
STDMETHODIMP MarshalInterface(
   __in IStream *pStm,
   __in REFIID riid,
   __in_opt void *pv,
   __in DWORD dwDestContext,
   __reserved void *pvDestContext,
   __in DWORD mshlflags
) override;
```

### <a name="parameters"></a>Parameter

*pStm*<br/>
Zeiger auf den Stream, der während des Marshalling verwendet werden.

*riid*<br/>
Verweis auf den Bezeichner der Schnittstelle, die gemarshallt werden soll. Diese Schnittstelle muss von abgeleitet werden die `IUnknown` Schnittstelle.

*PV*<br/>
Zeiger auf den Schnittstellenzeiger auf das zu marshallende; Wenn der Aufrufer nicht über einen Zeiger auf die gewünschte Schnittstelle verfügt, kann NULL sein.

*dwDestContext*<br/>
Zielkontext, in dem die angegebene Schnittstelle zum Marshalling rückgängig gemacht werden wird.

Geben Sie einen oder mehrere MSHCTX-Enumerationswerte.

Rückgängigmachen des Marshallens kann in ein anderes Apartment des aktuellen Prozesses (MSHCTX_INPROC) oder in einem anderen Prozess auf dem gleichen Computer wie der aktuelle Prozess (MSHCTX_LOCAL) auftreten.

*pvDestContext*<br/>
Für die zukünftige Verwendung reserviert. Muss 0 (null) sein.

*mshlflags*<br/>
Gibt an, ob die Daten gemarshallt werden zurück an den Prozess der übertragen werden – der Normalfall – oder in einer globalen Tabelle, in dem sie, indem mehrere Clients abgerufen werden geschrieben.

### <a name="return-value"></a>Rückgabewert

S_OK zurück, die der Schnittstellenzeiger auf erfolgreich gemarshallt wurde.

E_NOINTERFACE an die angegebene Schnittstelle wird nicht unterstützt.

STG_E_MEDIUMFULL der Datenstrom ist voll.

Fehler bei der E_FAIL den Vorgang.

## <a name="marshaller"></a>Ftmbase:: Marshaller_

Enthält einen Verweis auf die freethreaded Marshaller.

```cpp
Microsoft::WRL::ComPtr<IMarshal> marshaller_; ;
```

## <a name="releasemarshaldata"></a>Ftmbase:: ReleaseMarshalData

Zerstört ein gemarshalltes Datenpaket.

```cpp
STDMETHODIMP ReleaseMarshalData(
   __in IStream *pStm
) override;
```

### <a name="parameters"></a>Parameter

*pStm*<br/>
Zeiger auf ein Stream, der enthält das Datenpaket zerstört werden soll.

### <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls ein HRESULT, das den Fehler angibt.

## <a name="unmarshalinterface"></a>Ftmbase::: UnmarshalInterface

Initialisiert einen neu erstellten Proxy, und gibt einen Schnittstellenzeiger zurück, auf diesen Proxy.

```cpp
STDMETHODIMP UnmarshalInterface(
   __in IStream *pStm,
   __in REFIID riid,
   __deref_out void **ppv
) override;
```

### <a name="parameters"></a>Parameter

*pStm*<br/>
Zeiger auf der Stream, aus dem der Schnittstellenzeiger auf das Marshalling rückgängig gemacht werden.

*riid*<br/>
Verweis auf den Bezeichner der Schnittstelle an Marshalling rückgängig gemacht werden.

*ppv*<br/>
Wenn dieser Vorgang abgeschlossen ist, die Adresse einer Zeigervariablen, die die im angeforderten Schnittstellenzeiger empfängt *Riid*. Wenn dieser Vorgang erfolgreich ist, ist **Ppv* enthält den angeforderten Schnittstellenzeiger, der die Schnittstelle für das Marshalling rückgängig gemacht werden.

### <a name="return-value"></a>Rückgabewert

S_OK, wenn erfolgreich; andernfalls E_NOINTERFACE oder E_FAIL.
