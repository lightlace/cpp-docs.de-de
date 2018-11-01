---
title: 'TN064: Apartmentmodellthreading in ActiveX-Steuerelementen'
ms.date: 11/04/2016
f1_keywords:
- vc.controls.activex
helpviewer_keywords:
- OLE controls [MFC], container support
- containers [MFC], multithreaded
- TN064 [MFC]
- multithread container [MFC]
- apartment model threading [MFC]
ms.assetid: b2ab4c88-6954-48e2-9a74-01d4a60df073
ms.openlocfilehash: 37f8af1e4bd0fedf0b1ab14a90afdda3916c5391
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2018
ms.locfileid: "50665557"
---
# <a name="tn064-apartment-model-threading-in-activex-controls"></a>TN064: Apartmentmodellthreading in ActiveX-Steuerelementen

> [!NOTE]
>  Der folgende technische Hinweis wurde seit dem ersten Erscheinen in der Onlinedokumentation nicht aktualisiert. Daher können einige Verfahren und Themen veraltet oder falsch sein. Um aktuelle Informationen zu erhalten, wird empfohlen, das gewünschte Thema im Index der Onlinedokumentation zu suchen.

Diese technische Hinweis erläutert das threading-Apartment-Modell in einem ActiveX-Steuerelement zu aktivieren. Beachten Sie, dass threading-Apartment-Modell nur in Visual C++-Versionen 4.2 und höher unterstützt wird.

## <a name="what-is-apartment-model-threading"></a>Was ist das Threading-Apartment-Modell

Das Apartmentmodell ist ein Ansatz zur Unterstützung von eingebetteter Objekten, z. B. ActiveX-Steuerelemente in einer Multithread containeranwendung. Obwohl die Anwendung mehrere Threads möglicherweise, jede Instanz eines eingebetteten Objekts zugewiesen wird, ein "Apartment," die in nur einem Thread ausgeführt wird. Das heißt, werden alle Aufrufe in eine Instanz eines Steuerelements auf dem gleichen Thread ausgeführt.

Allerdings können verschiedene Instanzen des gleichen Typs des Steuerelements unterschiedlichen Apartments zugewiesen werden. Also, wenn mehrere Instanzen eines Steuerelements mit Daten im Common (z. B. globale oder statische Daten) gemeinsam nutzen, klicken Sie dann Zugriff auf diese freigegebenen Daten müssen durch ein Synchronisierungsobjekt, wie einem kritischen Abschnitt geschützt werden sollen.

Ausführliche Informationen in dem Apartment threading-Modell finden Sie unter [Prozesse und Threads](/windows/desktop/ProcThread/processes-and-threads) in die *OLE-Programmierreferenz*.

## <a name="why-support-apartment-model-threading"></a>Warum unterstützen Threading-Apartment-Modell

Steuerelemente, threading-Apartment-Modell unterstützen, können im Multithread-containeranwendungen verwendet werden, die auch das Apartmentmodell zu unterstützen. Wenn Sie die threading-Apartment-Modell nicht aktivieren, werden Sie die mögliche Gruppe von Containern einschränken, in denen das Steuerelement verwendet werden kann.

Aktivieren von threading-Apartment-Modell ist einfach für die meisten Steuerelemente, insbesondere, wenn sie nur wenig oder keine freigegebene Daten vorliegen.

## <a name="protecting-shared-data"></a>Schützen von freigegebenen Daten

Wenn das Steuerelement über freigegebene Daten verwendet z. B. eine statische Membervariable, der Zugriff auf, dass die Daten mit einem kritischen Abschnitt, um zu verhindern, dass mehrere Threads Ändern der Daten zur gleichen Zeit geschützt werden sollen. Deklarieren Sie zum Einrichten eines kritischen Abschnitts zu diesem Zweck eine statische Membervariable der Klasse `CCriticalSection` in der Klasse des Steuerelements. Verwenden der `Lock` und `Unlock` Memberfunktionen aus dem dieser kritischen Abschnitt Objekt, wo Ihr Code auf die freigegebenen Daten zugreift.

Betrachten Sie z. B. eine Steuerelementklasse, die eine Zeichenfolge zu verwalten, die von allen Instanzen gemeinsam verwendet werden muss. Diese Zeichenfolge kann in eine statische Membervariable verwaltet und durch einen kritischen Abschnitt geschützt werden. Klassendeklaration des Steuerelements würde Folgendes enthalten:

```
class CSampleCtrl : public COleControl
{
...
    static CString _strShared;
    static CCriticalSection _critSect;
};
```

Die Implementierung für die Klasse würde die Definitionen für diese Variablen enthalten:

```
int CString CSampleCtrl::_strShared;
CCriticalSection CSampleCtrl::_critSect;
```

Der Zugriff auf die `_strShared` statischer Member klicken Sie dann durch den kritischen Abschnitt geschützt werden kann:

```
void CSampleCtrl::SomeMethod()
{
    _critSect.Lock();
if (_strShared.Empty())
    _strShared = "<text>";
    _critSect.Unlock();

...
}
```

## <a name="registering-an-apartment-model-aware-control"></a>Registrieren ein Apartment-Modell-fähigen-Steuerelement

Steuerelemente, threading-Apartment-Modell unterstützen, sollte diese Funktion wird in der Registrierung durch Hinzufügen des benannten Werts "ThreadingModel" angeben, mit dem Wert "Apartment" in ihrer Klasse-ID-Registrierungseintrag unter der *Klassenkennung* \\ **InprocServer32** Schlüssel. Um die dazu führen, dass dieser Schlüssel für das Steuerelement automatisch registriert werden, übergeben die *AfxRegApartmentThreading* -Kennzeichen in der sechste Parameter `AfxOleRegisterControlClass`:

```
BOOL CSampleCtrl::CSampleCtrlFactory::UpdateRegistry(BOOL bRegister)
{
    if (bRegister)
    return AfxOleRegisterControlClass(
    AfxGetInstanceHandle(),
    m_clsid,
    m_lpszProgID,
    IDS_SAMPLE,
    IDB_SAMPLE,
    afxRegApartmentThreading,
    _dwSampleOleMisc,
    _tlid,
    _wVerMajor,
    _wVerMinor);

else
    return AfxOleUnregisterClass(m_clsid,
    m_lpszProgID);

}
```

Wenn das Projekt vom Assistent in Visual C++, Version 4.1 oder höher generiert wurde, wird dieses Flag bereits in Ihrem Code vorhanden sein. Es sind keine Änderungen erforderlich, um das Threadingmodell zu registrieren.

Wenn Ihr Projekt mit einer früheren Version der Assistent generiert wurde, weist Ihr vorhandene Code einen booleschen Wert wie der sechste Parameter auf. Wenn der vorhandene Parameter TRUE ist, ändern Sie ihn in *AfxRegInsertable | AfxRegApartmentThreading*. Wenn Sie der vorhandene Parameter auf false festgelegt ist, ändern Sie ihn in *AfxRegApartmentThreading*.

Wenn das Steuerelement nicht die Regeln für threading-Apartment-Modell entspricht, müssen Sie nicht übergeben *AfxRegApartmentThreading* in diesem Parameter.

## <a name="see-also"></a>Siehe auch

[Technische Hinweise – nach Nummern geordnet](../mfc/technical-notes-by-number.md)<br/>
[Technische Hinweise – nach Kategorien geordnet](../mfc/technical-notes-by-category.md)

