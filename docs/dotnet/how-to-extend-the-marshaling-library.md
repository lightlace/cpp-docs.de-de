---
title: 'Vorgehensweise: Erweitern der Marshallingbibliothek'
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- Marshaling Library, extending
ms.assetid: 4c4a56d7-1d44-4118-b85f-f9686515e6e9
ms.openlocfilehash: f289539807b1e9499cef51427d3f6a494545cc60
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62387304"
---
# <a name="how-to-extend-the-marshaling-library"></a>Vorgehensweise: Erweitern der Marshallingbibliothek

In diesem Thema wird erläutert, das Erweitern der Marshallingbibliothek, um weitere Umwandlungen zwischen Datentypen bereitzustellen. Benutzer können die Marshallingbibliothek für alle derzeit nicht unterstützt, von der Bibliothek datenkonvertierungen erweitern.

Sie können die Marshallingbibliothek auf zwei Arten – mit oder ohne Erweitern einer [Marshal_context-Klasse](../dotnet/marshal-context-class.md). Überprüfen Sie die [Overview of Marshaling in C++](../dotnet/overview-of-marshaling-in-cpp.md) Thema, um zu bestimmen, ob eine neue Konvertierung einen Kontext erfordert.

In beiden Fällen erstellen Sie zuerst eine Datei für die neue Marshalling Konvertierungen. Dies geschieht, um die Integrität des Standards Marshallingbibliothek erhalten. Wenn Sie ein Projekt auf einen anderen Computer oder ein anderer Programmierer portieren möchten, müssen Sie die neue Marshalling-Datei mit dem Rest des Projekts kopieren. Auf diese Weise kann der Benutzer das Projekt wird sichergestellt, dass die neuen Konvertierungen zu empfangen und muss keine Bibliotheksdateien zu ändern.

### <a name="to-extend-the-marshaling-library-with-a-conversion-that-does-not-require-a-context"></a>Zum Erweitern der Marshallingbibliothek bei einer Konvertierung erfordert, die einen Kontext keine

1. Erstellen Sie eine Datei zum Speichern der neuen Marshallen Funktionen, z. B. MyMarshal.h.

1. Umfassen Sie eine oder mehrere der Marshallingbibliotheksdateien:

   - Marshal.h für Basistypen.

   - marshal_windows.h für Windows-Datentypen.

   - marshal_cppstd.h für C++ Datentypen für Standard-Bibliothek.

   - marshal_atl.h für ATL-Datentypen.

1. Verwenden Sie den Code am Ende der folgenden Schritte aus, um die Konvertierungsfunktion zu schreiben. In diesem Code ist der Zieltyp der Konvertierung, FROM ist der Typ, aus dem konvertiert und `from` ist der Parameter konvertiert werden.

1. Ersetzen Sie den Kommentar zu Konvertierungslogik mit Code zum Konvertieren der `from` Parameter in ein Objekt des zu geben und das konvertierte Objekt zurückzugeben.

```
namespace msclr {
   namespace interop {
      template<>
      inline TO marshal_as<TO, FROM> (const FROM& from) {
         // Insert conversion logic here, and return a TO parameter.
      }
   }
}
```

### <a name="to-extend-the-marshaling-library-with-a-conversion-that-requires-a-context"></a>Zum Erweitern der Marshallingbibliothek bei einer Konvertierung erfordert, die einen Kontext

1. Erstellen Sie eine Datei zum Speichern von neuen Marshallen Funktionen, z. B. MyMarshal.h

1. Umfassen Sie eine oder mehrere der Marshallingbibliotheksdateien:

   - Marshal.h für Basistypen.

   - marshal_windows.h für Windows-Datentypen.

   - marshal_cppstd.h für C++ Datentypen für Standard-Bibliothek.

   - marshal_atl.h für ATL-Datentypen.

1. Verwenden Sie den Code am Ende der folgenden Schritte aus, um die Konvertierungsfunktion zu schreiben. In diesem Code ist der Zieltyp der Konvertierung, FROM ist der Typ, aus dem konvertiert `toObject` ist ein Zeiger in der das Ergebnis gespeichert und `fromObject` ist der Parameter konvertiert werden.

1. Ersetzen Sie den Kommentar zum Initialisieren von mit Code zum Initialisieren der `toPtr` auf den entsprechenden leeren Wert. Z. B. wenn es ein Zeiger ist, legen Sie es auf `NULL`.

1. Ersetzen Sie den Kommentar zu Konvertierungslogik mit Code zum Konvertieren der `from` Parameter in ein Objekt des *für* Typ. Dieser konvertierte Objekt gespeichert werden soll `toPtr`.

1. Ersetzen Sie den Kommentar zu den Einstellungen `toObject` mit Code aus, um `toObject` auf das konvertierte Objekt.

1. Ersetzen Sie den Kommentar zum Bereinigen von systemeigenen Ressourcen durch Code, um alle von belegten Arbeitsspeicher freizugeben `toPtr`. Wenn `toPtr` zugeordneter Arbeitsspeicher mit `new`, verwenden Sie `delete` um den Arbeitsspeicher freizugeben.

```
namespace msclr {
   namespace interop {
      template<>
      ref class context_node<TO, FROM> : public context_node_base
      {
      private:
         TO toPtr;
      public:
         context_node(TO& toObject, FROM fromObject)
         {
            // (Step 4) Initialize toPtr to the appropriate empty value.
            // (Step 5) Insert conversion logic here.
            // (Step 6) Set toObject to the converted parameter.
         }
         ~context_node()
         {
            this->!context_node();
         }
      protected:
         !context_node()
         {
            // (Step 7) Clean up native resources.
         }
      };
   }
}
```

## <a name="example"></a>Beispiel

Im folgende Beispiel erweitert die Marshallingbibliothek mit eine Konvertierung, die nicht mit einen Kontext erfordert. In diesem Beispiel konvertiert der Code aus einem systemeigenen Datentyp die Mitarbeiterdaten in einen verwalteten Datentyp an.

```
// MyMarshalNoContext.cpp
// compile with: /clr
#include <msclr/marshal.h>

value struct ManagedEmp {
   System::String^ name;
   System::String^ address;
   int zipCode;
};

struct NativeEmp {
   char* name;
   char* address;
   int zipCode;
};

namespace msclr {
   namespace interop {
      template<>
      inline ManagedEmp^ marshal_as<ManagedEmp^, NativeEmp> (const NativeEmp& from) {
         ManagedEmp^ toValue = gcnew ManagedEmp;
         toValue->name = marshal_as<System::String^>(from.name);
         toValue->address = marshal_as<System::String^>(from.address);
         toValue->zipCode = from.zipCode;
         return toValue;
      }
   }
}

using namespace System;
using namespace msclr::interop;

int main() {
   NativeEmp employee;

   employee.name = "Jeff Smith";
   employee.address = "123 Main Street";
   employee.zipCode = 98111;

   ManagedEmp^ result = marshal_as<ManagedEmp^>(employee);

   Console::WriteLine("Managed name: {0}", result->name);
   Console::WriteLine("Managed address: {0}", result->address);
   Console::WriteLine("Managed zip code: {0}", result->zipCode);

   return 0;
}
```

Im vorherigen Beispiel die `marshal_as` Funktion gibt ein Handle an die konvertierten Daten. Dies erfolgte, um zu verhindern, erstellen eine zusätzliche Kopie der Daten. Die Variable direkt zurückgeben würde eine unnötige Leistungseinbußen zugeordnet haben.

```Output
Managed name: Jeff Smith
Managed address: 123 Main Street
Managed zip code: 98111
```

## <a name="example"></a>Beispiel

Im folgende Beispiel werden die Informationen zu Mitarbeitern aus einem verwalteten Datentyp in einen systemeigenen Datentyp konvertiert. Diese Konvertierung erfordert einen Kontext an marshallen.

```
// MyMarshalContext.cpp
// compile with: /clr
#include <stdlib.h>
#include <string.h>
#include <msclr/marshal.h>

value struct ManagedEmp {
   System::String^ name;
   System::String^ address;
   int zipCode;
};

struct NativeEmp {
   const char* name;
   const char* address;
   int zipCode;
};

namespace msclr {
   namespace interop {
      template<>
      ref class context_node<NativeEmp*, ManagedEmp^> : public context_node_base
      {
      private:
         NativeEmp* toPtr;
         marshal_context context;
      public:
         context_node(NativeEmp*& toObject, ManagedEmp^ fromObject)
         {
            // Conversion logic starts here
            toPtr = NULL;

            const char* nativeName;
            const char* nativeAddress;

            // Convert the name from String^ to const char*.
            System::String^ tempValue = fromObject->name;
            nativeName = context.marshal_as<const char*>(tempValue);

            // Convert the address from String^ to const char*.
            tempValue = fromObject->address;
            nativeAddress = context.marshal_as<const char*>(tempValue);

            toPtr = new NativeEmp();
            toPtr->name = nativeName;
            toPtr->address = nativeAddress;
            toPtr->zipCode = fromObject->zipCode;

            toObject = toPtr;
         }
         ~context_node()
         {
            this->!context_node();
         }
      protected:
         !context_node()
         {
            // When the context is deleted, it will free the memory
            // allocated for toPtr->name and toPtr->address, so toPtr
            // is the only memory that needs to be freed.
            if (toPtr != NULL) {
               delete toPtr;
               toPtr = NULL;
            }
         }
      };
   }
}

using namespace System;
using namespace msclr::interop;

int main() {
   ManagedEmp^ employee = gcnew ManagedEmp();

   employee->name = gcnew String("Jeff Smith");
   employee->address = gcnew String("123 Main Street");
   employee->zipCode = 98111;

   marshal_context context;
   NativeEmp* result = context.marshal_as<NativeEmp*>(employee);

   if (result != NULL) {
      printf_s("Native name: %s\nNative address: %s\nNative zip code: %d\n",
         result->name, result->address, result->zipCode);
   }

   return 0;
}
```

```Output
Native name: Jeff Smith
Native address: 123 Main Street
Native zip code: 98111
```

## <a name="see-also"></a>Siehe auch

[Übersicht über das Marshalling in C++](../dotnet/overview-of-marshaling-in-cpp.md)
