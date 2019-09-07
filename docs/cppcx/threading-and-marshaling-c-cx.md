---
title: Threading und Marshalling (C++/CX)
ms.date: 12/30/2016
f1_keywords:
- C4451
helpviewer_keywords:
- threading issues, C++/CX
- agility, C++/CX
- C++/CX, threading issues
ms.assetid: 83e9ca1d-5107-4194-ae6f-e01bd928c614
ms.openlocfilehash: 05601367b6907e34d9d67364d35988a37ceae40c
ms.sourcegitcommit: 180f63704f6ddd07a4172a93b179cf0733fd952d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/06/2019
ms.locfileid: "70741129"
---
# <a name="threading-and-marshaling-ccx"></a>Threading und Marshalling (C++/CX)

In den meisten Fällen können Instanzen von Windows-Runtime Klassen, wie z. b C++ . Standardobjekte, von jedem beliebigen Thread aus aufgerufen werden. Solche Klassen werden als "agil" bezeichnet. Eine kleine Anzahl von Windows-Runtime Klassen, die mit Windows ausgeliefert werden, ist jedoch nicht agil und muss mehr wie COM-Objekte verwendet werden C++ , als Standardobjekte. Sie müssen zwar kein COM-Experte sein, um nicht agile Klassen zu verwenden, aber das Threadmodell dieser Klassen sowie ihr Marshallingverhalten beachten. Dieser Artikel ist ein Leitfaden für die seltenen Fälle, in denen Sie die Instanz einer nicht agilen Klasse verarbeiten müssen.

## <a name="threading-model-and-marshaling-behavior"></a>Threadmodell und Marshallingverhalten

Eine Windows-Runtime Klasse kann gleichzeitigen Thread Zugriff auf verschiedene Arten unterstützen, wie durch zwei Attribute angegeben, die darauf angewendet werden:

- Das Attribut`ThreadingModel` kann einen der Werte STA, MTA oder Both besitzen, die durch die Enumeration `ThreadingModel` definiert werden.

- Das Attribut`MarshallingBehavior` kann einen der Werte Agile, None oder Standard besitzen, die durch die Enumeration `MarshallingType` definiert werden.

Das Attribut `ThreadingModel` gibt an, wo die Klasse bei der Aktivierung geladen wird: Nur in einem Benutzeroberflächenthread-Kontext (STA), nur in einem Hintergrundthread-Kontext (MTA) oder im Kontext des Threads, der das Objekt erstellt (Both). Die Werte des `MarshallingBehavior` -Attributs beziehen sich darauf, wie sich das Objekt im jeweiligen Threadkontext verhält. In den meisten Fällen benötigen Sie keine Kenntnisse über diese Details.  Von den Klassen, die von der Windows-API bereitgestellt werden, haben ungefähr 90 Prozent `ThreadingModel`=Both und `MarshallingType`=Agile. Das bedeutet, dass sie Threadingdetails auf niedriger Ebene transparent und effizient verarbeiten können.   Wenn Sie `ref new` verwenden, um eine "agile" Klasse zu erstellen, können Sie Methoden dafür aus dem Haupt-App-Thread oder aus einem oder mehreren Arbeitsthreads aufrufen.  Das heißt, Sie können von jeder Stelle im Code aus eine agile Klasse verwenden – unabhängig davon, ob sie von Windows oder von einem Drittanbieter bereitgestellt wird. Sie müssen nicht auf das Threadingmodell oder das Marshallingverhalten der Klasse achten.

## <a name="consuming-windows-runtime-components"></a>Verarbeiten von Windows-Runtime-Komponenten

Wenn Sie eine universelle Windows-Plattform-app erstellen, können Sie sowohl mit Agile als auch mit nicht agilen Komponenten interagieren. Wenn Sie mit nicht agilen Komponenten interagieren, wird möglicherweise die folgende Warnung angezeigt.

### <a name="compiler-warning-c4451-when-consuming-non-agile-classes"></a>Compilerwarnung c4451 aus bei der Verwendung von nicht agilen Klassen

Aus verschiedenen Gründen können einige Klassen nicht agil sein. Wenn Sie auf Instanzen von nicht agilen Klassen sowohl über einen Benutzeroberflächenthread als auch über einen Hintergrundthread zugreifen, achten Sie besonders darauf, das richtige Verhalten zur Laufzeit sicherzustellen. Der Microsoft C++ -Compiler gibt Warnungen aus, wenn Sie eine nicht Agile Lauf Zeit Klasse in der APP im globalen Gültigkeitsbereich instanziieren oder einen nicht agilen Typ als Klassenmember in einer Verweis Klasse deklarieren, die selbst als Agile markiert ist.

Von den nicht agilen Klassen sind diejenigen am einfachsten zu behandeln, die `ThreadingModel`=Both und `MarshallingType`=Standard haben.  Sie können diese Klassen agil machen, indem Sie einfach die Hilfsklasse `Agile<T>` verwenden.   Das folgende Beispiel zeigt eine Deklaration eines nicht agilen Objekts des Typs `Windows::Security::Credentials::UI::CredentialPickerOptions^`und die Compilerwarnung, die infolgedessen ausgegeben wird.

```

ref class MyOptions
    {
    public:
        property Windows::Security::Credentials::UI::CredentialPickerOptions^ Options

        {
            Windows::Security::Credentials::UI::CredentialPickerOptions^ get()
            {
                return _myOptions;
            }
        }
    private:
        Windows::Security::Credentials::UI::CredentialPickerOptions^ _myOptions;
    };
```

Hier ist die Warnung, die ausgegeben wird:

> `Warning 1 warning C4451: 'Platform::Agile<T>::_object' : Usage of ref class 'Windows::Security::Credentials::UI::CredentialPickerOptions' inside this context can lead to invalid marshaling of object across contexts. Consider using 'Platform::Agile<Windows::Security::Credentials::UI::CredentialPickerOptions>' instead`

Wenn Sie einem Objekt mit dem Marshallingverhalten "Standard" einen Verweis – im Element Bereich oder globalen Gültigkeitsbereich hinzufügen – gibt der Compiler eine Warnung aus, die Sie dazu rät, den Typ `Platform::Agile<T>`in zu wrappen: `Consider using 'Platform::Agile<Windows::Security::Credentials::UI::CredentialPickerOptions>' instead`Wenn Sie verwenden `Agile<T>`, können Sie die-Klasse wie jede andere Agile-Klasse verwenden. Verwenden Sie in diesem Fall `Platform::Agile<T>` :

- Die nicht agile Variable wird im globalen Gültigkeitsbereich deklariert.

- Die nicht agile Variable wird im Klassengültigkeitsbereich deklariert, und es besteht die Möglichkeit, dass verwendeter Code den Zeiger einschmuggelt, d. h. ihn in einem anderen Apartment ohne das richtige Marshalling verwendet.

Ist keine dieser Bedingungen zutreffend, können Sie die enthaltende Klasse als nicht agil markieren. Mit anderen Worten, Sie sollten nicht Agile Objekte direkt nur in nicht agilen Klassen halten und nicht Agile Objekte über Platform:: Agile\<T > in Agile-Klassen speichern.

Im folgenden Beispiel wird gezeigt, wie Sie `Agile<T>` verwenden müssen, damit Sie die Warnung sicher ignorieren können.

```

#include <agile.h>
ref class MyOptions
    {
    public:
        property Windows::Security::Credentials::UI::CredentialPickerOptions^ Options

        {
            Windows::Security::Credentials::UI::CredentialPickerOptions^ get()
            {
                return m_myOptions.Get();
            }
        }
    private:
        Platform::Agile<Windows::Security::Credentials::UI::CredentialPickerOptions^> m_myOptions;

    };
```

Beachten Sie, dass `Agile` nicht als Rückgabewert oder Parameter in einer Verweisklasse übergeben werden kann. Die Methode `Agile<T>::Get()` gibt ein "handle-to-object" (^) zurück, das Sie über die Anwendungsbinärdateischnittstelle (ABI) in einer öffentlichen Methode oder Eigenschaft übergeben können.

Wenn Sie einen Verweis auf eine in-proc-Windows-Runtime Klasse erstellen, die das Marshallingverhalten "None" aufweist, gibt der Compiler eine Warnung aus c4451 aus aber es wird nicht `Platform::Agile<T>`empfohlen, die Verwendung von in Erwägung zu nehmen.  Der Compiler kann über diese Warnung hinaus keine Hilfe anbieten, sodass es in Ihrer Verantwortung liegt, die Klasse richtig zu verwenden und sicherzustellen, dass der Code STA-Komponenten nur aus dem Benutzeroberflächenthread und MTA-Komponenten nur aus einem Hintergrundthread aufruft.

## <a name="authoring-agile-windows-runtime-components"></a>Erstellen von Agile-Windows-Runtime Komponenten

Wenn Sie in C++/CX eine Verweis Klasse definieren, ist Sie standardmäßig agil – das heißt, Sie `ThreadingModel`hat = both `MarshallingType`und = Agile.  Wenn Sie die Windows-Runtime C++ Vorlagen Bibliothek verwenden, können Sie die Klasse agil machen, indem Sie `FtmBase`von ableiten `FreeThreadedMarshaller`, das verwendet.  Wenn Sie eine Klasse erstellen, die `ThreadingModel`=Both oder `ThreadingModel`=MTA hat, überprüfen Sie, ob die Klasse threadsicher ist.

Sie können das Threadingmodell und das Marshallingverhalten einer Verweisklasse ändern. Wenn Sie Änderungen vornehmen, die die Klasse zu "nicht agil" rendern, müssen Sie die Auswirkungen verstehen, die mit diesen Änderungen verbunden sind.

Im folgenden Beispiel wird gezeigt, wie `MarshalingBehavior` - `ThreadingModel` und-Attribute auf eine Lauf Zeit Klasse in einer Windows-Runtime-Klassenbibliothek angewendet werden. Wenn eine App die DLL verwendet und das Schlüsselwort `ref new` benutzt, um ein `MySTAClass` -Klassenobjekt zu aktivieren, ist das Objekt in einem Singlethread-Apartment aktiviert und unterstützt kein Marshalling.

```
using namespace Windows::Foundation::Metadata;
using namespace Platform;

[Threading(ThreadingModel::STA)]
[MarshalingBehavior(MarshalingType::None)]
public ref class MySTAClass
{
};
```

In einer unversiegelten Klasse müssen die Marshalling- und Threadingattribute festgelegt sein, damit der Compiler überprüfen kann, ob abgeleitete Klassen für diese Attribute den gleichen Wert haben. Wenn die Klasse diese Einstellungen nicht aufweist, generiert der Compiler einen Fehler, und es findet keine Kompilierung statt. Jede Klasse, die von einer unversiegelten Klasse abgeleitet ist, generiert in den folgenden Fällen einen Compilerfehler:

- Die Attribute `ThreadingModel` und `MarshallingBehavior` sind in der abgeleiteten Klasse nicht definiert.

- Die Werte der Attribute `ThreadingModel` und `MarshallingBehavior` stimmen in der abgeleiteten Klasse nicht mit denen in der Basisklasse überein.

Die Threading-und Marshallinginformationen, die von einer Drittanbieter-Windows-Runtime Komponente benötigt werden, werden in den Registrierungsinformationen für das App-Manifest für die Komponente angegeben. Es wird empfohlen, dass Sie alle Ihre Windows-Runtime Komponenten Agile machen. Dadurch wird sichergestellt, dass Clientcode die Komponente von jedem Thread in der App aufrufen kann. Außerdem wird dadurch die Leistung dieser Aufrufe verbessert, da sie direkte Aufrufe sind, die kein Marshalling haben. Wenn Sie die Klasse auf diese Weise erstellen, braucht Clientcode `Platform::Agile<T>` nicht zu verwenden, um die Klasse zu nutzen.

## <a name="see-also"></a>Siehe auch

[ThreadingModel](/uwp/api/Windows.Foundation.Metadata.ThreadingModel)<br/>
[MarshallingBehavior](/uwp/api/windows.foundation.metadata.marshalingbehaviorattribute)
