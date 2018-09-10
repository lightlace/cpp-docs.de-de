---
title: Threading und Marshalling (C++ / CX) | Microsoft-Dokumentation
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: language-reference
f1_keywords:
- C4451
helpviewer_keywords:
- threading issues, C++/CX
- agility, C++/CX
- C++/CX, threading issues
ms.assetid: 83e9ca1d-5107-4194-ae6f-e01bd928c614
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3e02f69efb5658225f40f2c6dfcd74801bd04929
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/07/2018
ms.locfileid: "44100417"
---
# <a name="threading-and-marshaling-ccx"></a>Threading und Marshalling (C++/CX)

In der Mehrzahl der Fälle können Instanzen von Windows-Runtime-Klassen wie Standard-c++-Objekten, von jedem Thread aus zugegriffen werden. Solche Klassen werden als "agil" bezeichnet. Allerdings eine kleine Anzahl von Windows-Runtime-Klassen, die mit Windows ausgeliefert werden nicht agilen und mehr verarbeitet werden muss, z. B. com-Objekte als Standard-c++-Objekten. Sie müssen zwar kein COM-Experte sein, um nicht agile Klassen zu verwenden, aber das Threadmodell dieser Klassen sowie ihr Marshallingverhalten beachten. Dieser Artikel ist ein Leitfaden für die seltenen Fälle, in denen Sie die Instanz einer nicht agilen Klasse verarbeiten müssen.

## <a name="threading-model-and-marshaling-behavior"></a>Threadmodell und Marshallingverhalten

Eine Windows-Runtime-Klasse kann gleichzeitigen Threadzugriff auf verschiedene Weise unterstützen, wie durch zwei Attribute angegeben werden, die darauf angewendet werden:

- Das Attribut`ThreadingModel` kann einen der Werte STA, MTA oder Both besitzen, die durch die Enumeration `ThreadingModel` definiert werden.

- Das Attribut`MarshallingBehavior` kann einen der Werte Agile, None oder Standard besitzen, die durch die Enumeration `MarshallingType` definiert werden.

Das Attribut `ThreadingModel` gibt an, wo die Klasse bei der Aktivierung geladen wird: Nur in einem Benutzeroberflächenthread-Kontext (STA), nur in einem Hintergrundthread-Kontext (MTA) oder im Kontext des Threads, der das Objekt erstellt (Both). Die Werte des `MarshallingBehavior` -Attributs beziehen sich darauf, wie sich das Objekt im jeweiligen Threadkontext verhält. In den meisten Fällen benötigen Sie keine Kenntnisse über diese Details.  Von den Klassen, die von der Windows-API bereitgestellt werden, haben ungefähr 90 Prozent `ThreadingModel`=Both und `MarshallingType`=Agile. Das bedeutet, dass sie Threadingdetails auf niedriger Ebene transparent und effizient verarbeiten können.   Wenn Sie `ref new` verwenden, um eine "agile" Klasse zu erstellen, können Sie Methoden dafür aus dem Haupt-App-Thread oder aus einem oder mehreren Arbeitsthreads aufrufen.  Das heißt, Sie können von jeder Stelle im Code aus eine agile Klasse verwenden – unabhängig davon, ob sie von Windows oder von einem Drittanbieter bereitgestellt wird. Sie müssen nicht auf das Threadingmodell oder das Marshallingverhalten der Klasse achten.

## <a name="consuming-windows-runtime-components"></a>Verarbeiten von Windows-Runtime-Komponenten

Wenn Sie eine universelle Windows-Plattform-app erstellen, können Sie mit sowohl bewegliche als auch nicht agilen Komponenten interagieren. Wenn Sie mit nicht agilen Komponenten interagieren, wird möglicherweise die folgende Warnung angezeigt.

### <a name="compiler-warning-c4451-when-consuming-non-agile-classes"></a>Warnung C4451 aus, bei der Nutzung von nicht agilen Klassen

Aus verschiedenen Gründen können einige Klassen nicht agil sein. Wenn Sie auf Instanzen von nicht agilen Klassen sowohl über einen Benutzeroberflächenthread als auch über einen Hintergrundthread zugreifen, achten Sie besonders darauf, das richtige Verhalten zur Laufzeit sicherzustellen. Der Visual C++-Compiler gibt Warnungen aus, wenn Sie eine nicht agile Laufzeitklasse in der App im globalen Gültigkeitsbereich instanziieren oder einen nicht agilen Typ als Klassenmember in einer Verweisklasse deklarieren, die selbst als agil gekennzeichnet ist.

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

Wenn Sie im Member- oder im globalen Gültigkeitsbereich zu einem Objekt einen Verweis hinzufügen, der das Marshallingverhalten "Standard" hat, gibt der Compiler eine Warnung aus, die Sie auffordert, den Typ stattdessen in `Platform::Agile<T>`: `Consider using 'Platform::Agile<Windows::Security::Credentials::UI::CredentialPickerOptions>' instead` zu umschließen. Wenn Sie `Agile<T>`verwenden, können Sie die Klasse wie jede andere agile Klasse nutzen. Verwenden Sie in diesem Fall `Platform::Agile<T>` :

- Die nicht agile Variable wird im globalen Gültigkeitsbereich deklariert.

- Die nicht agile Variable wird im Klassengültigkeitsbereich deklariert, und es besteht die Möglichkeit, dass verwendeter Code den Zeiger einschmuggelt, d. h. ihn in einem anderen Apartment ohne das richtige Marshalling verwendet.

Ist keine dieser Bedingungen zutreffend, können Sie die enthaltende Klasse als nicht agil markieren. Das heißt, Sie sollten direkt nicht agile Objekte nur in nicht agilen Klassen halten und nicht agile Objekte über Platform:: Agile\<T > in agilen Klassen.

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

In Visual C++, wenn Sie einen Verweis auf ein in-Proc-Windows-Runtime-Klasse erstellen, die ein Marshallingverhalten von "None", hat der Compiler gibt die Warnung C4451 aus, jedoch nicht vor, dass Sie erwägen, `Platform::Agile<T>`.  Der Compiler kann über diese Warnung hinaus keine Hilfe anbieten, sodass es in Ihrer Verantwortung liegt, die Klasse richtig zu verwenden und sicherzustellen, dass der Code STA-Komponenten nur aus dem Benutzeroberflächenthread und MTA-Komponenten nur aus einem Hintergrundthread aufruft.

## <a name="authoring-agile-windows-runtime-components"></a>Erstellen von agile-Windows-Runtime-Komponenten

Beim Definieren einer Verweisklasse in C++ / CX, wird sie standardmäßig agil – das heißt, er hat `ThreadingModel`= Both und `MarshallingType`= Agile.  Wenn Sie die Windows Runtime C++ Template Library verwenden, Sie können die Klasse agil machen durch Ableiten von `FtmBase`, verwendet der `FreeThreadedMarshaller`.  Wenn Sie eine Klasse erstellen, die `ThreadingModel`=Both oder `ThreadingModel`=MTA hat, überprüfen Sie, ob die Klasse threadsicher ist.

Sie können das Threadingmodell und das Marshallingverhalten einer Verweisklasse ändern. Wenn Sie Änderungen vornehmen, die die Klasse zu "nicht agil" rendern, müssen Sie die Auswirkungen verstehen, die mit diesen Änderungen verbunden sind.

Das folgende Beispiel zeigt, wie Sie anwenden `MarshalingBehavior` und `ThreadingModel` Attribute auf eine Laufzeitklasse in einer Windows-Runtime-Klassenbibliothek. Wenn eine App die DLL verwendet und das Schlüsselwort `ref new` benutzt, um ein `MySTAClass` -Klassenobjekt zu aktivieren, ist das Objekt in einem Singlethread-Apartment aktiviert und unterstützt kein Marshalling.

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

Die Threading- und Marshallinginformationen, die von einer Drittanbieter-Windows-Runtime-Komponente erforderlich ist, wird in der app-manifestregistrierungsinformationen für die Komponente angegeben. Es wird empfohlen, dass Sie alle Ihre Windows-Runtime-Komponenten für agile vornehmen. Dadurch wird sichergestellt, dass Clientcode die Komponente von jedem Thread in der App aufrufen kann. Außerdem wird dadurch die Leistung dieser Aufrufe verbessert, da sie direkte Aufrufe sind, die kein Marshalling haben. Wenn Sie die Klasse auf diese Weise erstellen, braucht Clientcode `Platform::Agile<T>` nicht zu verwenden, um die Klasse zu nutzen.

## <a name="see-also"></a>Siehe auch

[ThreadingModel](https://msdn.microsoft.com/library/windows/apps/xaml/windows.foundation.metadata.threadingmodel.aspx)<br/>
[MarshallingBehavior](https://msdn.microsoft.com/library/windows/apps/xaml/windows.foundation.metadata.marshalingbehaviorattribute.aspx)