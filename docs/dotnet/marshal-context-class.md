---
title: marshal_context-Klasse
ms.date: 01/16/2019
ms.topic: reference
f1_keywords:
- msclr::interop::marshal_context::marshal_context
- msclr::interop::marshal_context::marshal_as
helpviewer_keywords:
- msclr::marshal_context class [C++]
ms.assetid: 241b0cf6-4ca4-4812-aaee-d671c11dc034
ms.openlocfilehash: 25fc2be80ba0e5d8c7f76cee1f22eed4d1bb4fc7
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "62384867"
---
# <a name="marshalcontext-class"></a>marshal_context-Klasse

Diese Klasse konvertiert die Daten zwischen nativen und verwalteten Umgebungen.

## <a name="syntax"></a>Syntax

```cpp
class marshal_context
```

## <a name="remarks"></a>Hinweise

Verwenden der `marshal_context` -Klasse für die Konvertierung von Daten, die einen Kontext erfordern. Weitere Informationen zu welche Konvertierungen einen Kontext benötigen und welche Marshalling-Datei eingeschlossen werden muss, finden Sie unter [Überblick über das Marshalling in C++](../dotnet/overview-of-marshaling-in-cpp.md). Das Ergebnis des Marshallens wird bei der Verwendung von eines Kontexts ist nur gültig bis zum die `marshal_context` -Objekt zerstört wird. Um das Ergebnis zu erhalten, müssen Sie die Daten kopieren.

Die gleiche `marshal_context` für zahlreiche datenkonvertierungen verwendet werden kann. Wiederverwenden von den Kontext auf diese Weise hat keine Auswirkungen, auf die Ergebnisse der vorherigen Marshalling aufrufen.

## <a name="members"></a>Member

### <a name="public-constructors"></a>Öffentliche Konstruktoren

|Name|Beschreibung| 
|---------|-----------| 
|[marshal_context::marshal_context](#marshal-context)|Erstellt eine `marshal_context` Objekt, für die Datenkonvertierung zwischen verwalteten und systemeigenen Datentypen verwendet werden.| 
|[marshal_context::~marshal_context](#tilde-marshal-context)|Zerstört ein `marshal_context`-Objekt.| 

### <a name="public-methods"></a>Öffentliche Methoden

|Name|Beschreibung| 
|---------|-----------| 
|[marshal_context::marshal_as](#marshal-as)|Führt das Marshalling für ein bestimmtes Objekt zwischen einer verwalteten und nativer Datentyp konvertieren.| 


## <a name="requirements"></a>Anforderungen

**Headerdatei:** \<msclr\marshal.h >, \<msclr\marshal_windows.h >, \<msclr\marshal_cppstd.h >, oder \<msclr\marshal_atl.h >

**Namespace:** msclr::interop

## <a name="marshal-context"></a>marshal_context::marshal_context

Erstellt eine `marshal_context` Objekt, für die Datenkonvertierung zwischen verwalteten und systemeigenen Datentypen verwendet werden.

```cpp
marshal_context();
```

### <a name="remarks"></a>Hinweise

Einige datenkonvertierungen erfordern einen Kontext gemarshallt. Weitere Informationen darüber, welche Übersetzungen erfordern einen Kontext und Marshalling von der Datei, die Sie in Ihrer Anwendung enthalten, finden Sie unter [Überblick über das Marshalling in C++](../dotnet/overview-of-marshaling-in-cpp.md).

### <a name="example"></a>Beispiel

Siehe das Beispiel für [marshal_context::marshal_as](../dotnet/marshal-context-marshal-as.md).


## <a name="tilde-marshal-context"></a>marshal_context::~marshal_context

Zerstört ein `marshal_context`-Objekt.

```cpp
~marshal_context();
```

### <a name="remarks"></a>Hinweise

Einige datenkonvertierungen erfordern einen Kontext gemarshallt. Finden Sie unter [Überblick über das Marshalling in C++](../dotnet/overview-of-marshaling-in-cpp.md) für Weitere Informationen zu der Übersetzungen einen Kontext benötigen und welche Marshalling-Datei muss in Ihrer Anwendung einbezogen werden.

Löschen einer `marshal_context` Objekt werden die Daten konvertiert, die von diesem Kontext ungültig. Wenn Sie Ihre Daten nach dem beibehalten möchten eine `marshal_context` -Objekt zerstört wird, müssen Sie die Daten manuell kopieren, auf eine Variable, die beibehalten werden.

## <a name="marshal-as"></a>marshal_context::marshal_as

Führt das Marshalling für ein bestimmtes Objekt zwischen einer verwalteten und nativer Datentyp konvertieren.

```cpp
To_Type marshal_as<To_Type>(
   From_Type input
);
```

### <a name="parameters"></a>Parameter

*input*<br/>
[in] Der Wert, der zum Marshallen soll eine `To_Type` Variable.

### <a name="return-value"></a>Rückgabewert

Eine Variable vom Typ `To_Type` ist der konvertierte Wert vom `input`.

### <a name="remarks"></a>Hinweise

Diese Funktion führt das Marshalling für ein bestimmtes Objekt. Verwenden Sie diese Funktion nur für die Konvertierungen, die von der Tabelle im angegebenen [Überblick über das Marshalling in C++](../dotnet/overview-of-marshaling-in-cpp.md).

Wenn Sie versuchen, ein Paar von Datentypen zu marshallen, die nicht unterstützt, aber `marshal_as` generiert einen Fehler [C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md) zum Zeitpunkt der Kompilierung. Weitere Informationen zu dem Fehler finden Sie in der zugehörigen Meldung. Der Fehler `C4996` kann auch bei anderen Problemen als veralteten Funktionen generiert werden. Zwei Bedingungen, die diesen Fehler zu generieren möchten, ein Paar von Datentypen zu marshallen, die nicht unterstützt werden und verwenden möchten `marshal_as` für eine Konvertierung, die einen Kontext erfordert.

Die Marshallingbibliothek besteht aus mehreren Headerdateien. Für jede Konvertierung ist nur eine Datei erforderlich, Sie können bei Bedarf jedoch zusätzliche Dateien für andere Konvertierungen einbinden. Die Tabelle in `Marshaling Overview in C++` gibt an, welche Marshalling-Datei für jede Konvertierung enthalten sein sollten.

### <a name="example"></a>Beispiel

In diesem Beispiel erstellt einen Kontext für das Marshalling von einem `System::String` zu einem `const char *` Variablentyp. Die konvertierten Daten wird nicht nach der Zeile gültig, die den Kontext löscht.

```cpp
// marshal_context_test.cpp
// compile with: /clr
#include <stdlib.h>
#include <string.h>
#include <msclr\marshal.h>

using namespace System;
using namespace msclr::interop;

int main() {
   marshal_context^ context = gcnew marshal_context();
   String^ message = gcnew String("Test String to Marshal");
   const char* result;
   result = context->marshal_as<const char*>( message );
   delete context;
   return 0;
}
```