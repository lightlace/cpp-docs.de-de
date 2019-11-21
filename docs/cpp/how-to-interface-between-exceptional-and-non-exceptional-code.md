---
title: 'How to: Interface between exceptional and non-exceptional code'
ms.custom: how-to
ms.date: 11/19/2019
ms.topic: conceptual
ms.assetid: fd5bb4af-5665-46a1-a321-614b48d4061e
ms.openlocfilehash: fccc40302ab7bd43b3e6b2f87eef488c7813c9be
ms.sourcegitcommit: 654aecaeb5d3e3fe6bc926bafd6d5ace0d20a80e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/20/2019
ms.locfileid: "74245612"
---
# <a name="how-to-interface-between-exceptional-and-non-exceptional-code"></a>How to: Interface between exceptional and non-exceptional code

In diesem Artikel wird beschrieben, wie die konsistente Ausnahmebehandlung in einem C++-Modul implementiert wird und wie diese Ausnahmen zu und von Fehlercodes an den Ausnahmegrenzen übertragen werden.

Manchmal muss ein C++-Modul eine Verbindung mit Code herstellen, der keine Ausnahmen verwendet (Nicht-Ausnahmecode). Such an interface is known as an *exception boundary*. Sie können z. B. die Win32-Funktion `CreateFile` im C++-Programm aufrufen. `CreateFile` löst keine Ausnahmen aus. Stattdessen werden Fehlercodes festgelegt, die von der `GetLastError`-Funktion abgerufen werden können. Wenn das C++-Programm wichtig ist, möchten Sie vielleicht über eine konsistente ausnahmenbasierte Fehlerbehandlungsrichtlinie für das Programm verfügen. Und Sie möchten wahrscheinlich keine Ausnahmen verwerfen, nur weil Sie über eine Verbindung mit Nicht-Ausnahmencode verfügen. Ebenso wenig möchten Sie auf Ausnahmen basierende und nicht auf Ausnahmen basierende Fehlerrichtlinien im C++-Modul kombinieren.

## <a name="calling-non-exceptional-functions-from-c"></a>Calling non-exceptional functions from C++

Wenn Sie eine Nicht-Ausnahmefunktion von C++ aufrufen, kann diese Funktion in einer C++-Funktion umschlossen werden, die alle Fehler erkennt und dann möglicherweise eine Ausnahme auslöst. Beim Entwerfen einer solchen Wrapperfunktion legen Sie zuerst fest, welche Art von Ausnahmegarantie bereitgestellt wird: die starke Garantie, die grundlegende Garantie oder die Nothrow-Garantie. Als nächstes entwerfen Sie die Funktion so, dass alle Ressourcen, z. B. Dateihandles, ordnungsgemäß freigegeben werden, wenn eine Ausnahme ausgelöst wird. In der Regel bedeutet dies, dass Sie intelligente Zeiger oder ähnliche Ressourcen-Manager zum Erwerben der Ressourcen verwenden. For more information about design considerations, see [How to: Design for Exception Safety](how-to-design-for-exception-safety.md).

### <a name="example"></a>Beispiel

Das folgende Beispiel zeigt C++-Funktionen, die die Win32-Funktionen `CreateFile` und `ReadFile` intern verwenden, um zwei Dateien zu öffnen und zu lesen.  Die `File`-Klasse ist ein RAII-Wrapper (Resource Acquisition Is Initialization) für die Dateihandles. Sein Konstruktor erkennt den Zustand "Datei nicht gefunden" und löst eine Ausnahme aus, um den Fehler in der Aufrufliste des C++-Moduls weiterzugeben (in diesem Beispiel die `main()`-Funktion.) Wenn eine Ausnahme ausgelöst wird, nachdem ein `File`-Objekt vollständig erstellt wurde, ruft der Destruktor automatisch `CloseHandle` auf, um das Dateihandle freizugeben. (If you prefer, you can use the Active Template Library (ATL) `CHandle` class for this same purpose, or a `unique_ptr` together with a custom deleter.) The functions that call Win32 and CRT APIs detect errors and then throw C++ exceptions using the locally-defined `ThrowLastErrorIf` function, which in turn uses the `Win32Exception` class, derived from the `runtime_error` class. Alle Funktionen in diesem Beispiel stellen eine starke Ausnahmegarantie bereit. Wenn an irgendeinem Punkt in diesen Funktionen eine Ausnahme ausgelöst wird, kommt es nicht zum Verlust von Ressourcen und es wird keine Programmzustand geändert.

```cpp
// compile with: /EHsc
#include <Windows.h>
#include <stdlib.h>
#include <vector>
#include <iostream>
#include <string>
#include <limits>
#include <stdexcept>

using namespace std;

string FormatErrorMessage(DWORD error, const string& msg)
{
    static const int BUFFERLENGTH = 1024;
    vector<char> buf(BUFFERLENGTH);
    FormatMessageA(FORMAT_MESSAGE_FROM_SYSTEM, 0, error, 0, buf.data(),
        BUFFERLENGTH - 1, 0);
    return string(buf.data()) + "   ("  + msg  + ")";
}

class Win32Exception : public runtime_error
{
private:
    DWORD m_error;
public:
    Win32Exception(DWORD error, const string& msg)
        : runtime_error(FormatErrorMessage(error, msg)), m_error(error) { }

    DWORD GetErrorCode() const { return m_error; }
};

void ThrowLastErrorIf(bool expression, const string& msg)
{
    if (expression) {
        throw Win32Exception(GetLastError(), msg);
    }
}

class File
{
private:
    HANDLE m_handle;

    // Declared but not defined, to avoid double closing.
    File& operator=(const File&);
    File(const File&);
public:
    explicit File(const string& filename)
    {
        m_handle = CreateFileA(filename.c_str(), GENERIC_READ, FILE_SHARE_READ,
            nullptr, OPEN_EXISTING, FILE_ATTRIBUTE_READONLY, nullptr);
        ThrowLastErrorIf(m_handle == INVALID_HANDLE_VALUE,
            "CreateFile call failed on file named " + filename);
    }

    ~File() { CloseHandle(m_handle); }

    HANDLE GetHandle() { return m_handle; }
};

size_t GetFileSizeSafe(const string& filename)
{
    File fobj(filename);
    LARGE_INTEGER filesize;

    BOOL result = GetFileSizeEx(fobj.GetHandle(), &filesize);
    ThrowLastErrorIf(result == FALSE, "GetFileSizeEx failed: " + filename);

    if (filesize.QuadPart < (numeric_limits<size_t>::max)()) {
        return filesize.QuadPart;
    } else {
        throw;
    }
}

vector<char> ReadFileVector(const string& filename)
{
    File fobj(filename);
    size_t filesize = GetFileSizeSafe(filename);
    DWORD bytesRead = 0;

    vector<char> readbuffer(filesize);

    BOOL result = ReadFile(fobj.GetHandle(), readbuffer.data(), readbuffer.size(),
        &bytesRead, nullptr);
    ThrowLastErrorIf(result == FALSE, "ReadFile failed: " + filename);

    cout << filename << " file size: " << filesize << ", bytesRead: "
        << bytesRead << endl;

    return readbuffer;
}

bool IsFileDiff(const string& filename1, const string& filename2)
{
    return ReadFileVector(filename1) != ReadFileVector(filename2);
}

#include <iomanip>

int main ( int argc, char* argv[] )
{
    string filename1("file1.txt");
    string filename2("file2.txt");

    try
    {
        if(argc > 2) {
            filename1 = argv[1];
            filename2 = argv[2];
        }

        cout << "Using file names " << filename1 << " and " << filename2 << endl;

        if (IsFileDiff(filename1, filename2)) {
            cout << "+++ Files are different." << endl;
        } else {
            cout<< "=== Files match." << endl;
        }
    }
    catch(const Win32Exception& e)
    {
        ios state(nullptr);
        state.copyfmt(cout);
        cout << e.what() << endl;
        cout << "Error code: 0x" << hex << uppercase << setw(8) << setfill('0')
            << e.GetErrorCode() << endl;
        cout.copyfmt(state); // restore previous formatting
    }
}
```

## <a name="calling-exceptional-code-from-non-exceptional-code"></a>Calling exceptional code from non-exceptional code

C++-Funktionen, die als "extern C" deklariert sind, können von C-Programmen aufgerufen werden. C++-COM-Server können von Code genutzt werden, der in einer von mehreren verschiedenen Sprachen geschrieben wurde. Wenn Sie öffentliche ausnahmenbasierte Funktionen in C++ implementieren, die von Nicht-Ausnahmecode aufgerufen werden sollen, darf die C++-Funktion nicht zulassen, dass Ausnahmen wieder an den Aufrufer übergeben werden. Daher muss die C++-Funktion jede Ausnahme explizit abfangen, die sie behandeln kann, und die Ausnahme ggf. in einen Fehlercode konvertieren, den der Aufrufer versteht. Wenn nicht alle möglichen Ausnahmen bekannt sind, sollte die C++-Funktionen über einen `catch(...)`-Block als letzten Handler verfügen. In diesem Fall empfiehlt es sich, dem Aufrufer einen schwerwiegenden Fehler zu melden, da das Programm sich in einem unbekannten Zustand befinden könnte.

Das folgende Beispiel zeigt eine Funktion, die voraussetzt, dass es sich bei jeder möglicherweise ausgelösten Ausnahme entweder um den Typ "Win32Exception" handelt oder um einen Ausnahmetyp, der von `std::exception` abgeleitet wird. Die Funktion fängt jede Ausnahme dieser Typen ab und gibt die Fehlerinformationen als Win32-Fehlercode an den Aufrufer weiter.

```cpp
BOOL DiffFiles2(const string& file1, const string& file2)
{
    try
    {
        File f1(file1);
        File f2(file2);
        if (IsTextFileDiff(f1, f2))
        {
            SetLastError(MY_APPLICATION_ERROR_FILE_MISMATCH);
            return FALSE;
        }
        return TRUE;
    }
    catch(Win32Exception& e)
    {
        SetLastError(e.GetErrorCode());
    }

    catch(std::exception& e)
    {
        SetLastError(MY_APPLICATION_GENERAL_ERROR);
    }
    return FALSE;
}
```

Bei Konvertierungen von Ausnahmen in Fehlercodes besteht ein mögliches Problem darin, dass Fehlercodes häufig nicht die umfangreichen Informationen enthalten, die eine Ausnahme speichern kann. To address this, you can provide a **catch** block for each specific exception type that might be thrown, and perform logging to record the details of the exception before it is converted to an error code. This approach can create a lot of code repetition if multiple functions all use the same set of **catch** blocks. A good way to avoid code repetition is by refactoring those blocks into one private utility function that implements the **try** and **catch** blocks and accepts a function object that is invoked in the **try** block. Übergeben Sie den Code in jeder öffentlichen Funktion als Lambda-Ausdruck an die Hilfsfunktion.

```cpp
template<typename Func>
bool Win32ExceptionBoundary(Func&& f)
{
    try
    {
        return f();
    }
    catch(Win32Exception& e)
    {
        SetLastError(e.GetErrorCode());
    }
    catch(const std::exception& e)
    {
        SetLastError(MY_APPLICATION_GENERAL_ERROR);
    }
    return false;
}
```

Das folgende Beispiel zeigt, wie der Lambdaausdruck geschrieben wird, der das Funktionselement definiert. Wenn ein Funktionselement „inline“ mithilfe eines Lambdaausdrucks definiert wird, ist es oft besser lesbar, als wenn es als benanntes Funktionsobjekt geschrieben worden wäre.

```cpp
bool DiffFiles3(const string& file1, const string& file2)
{
    return Win32ExceptionBoundary([&]() -> bool
    {
        File f1(file1);
        File f2(file2);
        if (IsTextFileDiff(f1, f2))
        {
            SetLastError(MY_APPLICATION_ERROR_FILE_MISMATCH);
            return false;
        }
        return true;
    });
}
```

Weitere Informationen zu Lambdaausdrücken finden Sie unter [Lambda Expressions (Lambdaausdrücke)](lambda-expressions-in-cpp.md).

## <a name="see-also"></a>Siehe auch

[Modern C++ best practices for exceptions and error handling](errors-and-exception-handling-modern-cpp.md)<br/>
[Vorgehensweise: Entwurfsrichtlinien für sichere Ausnahmebehandlung](how-to-design-for-exception-safety.md)<br/>
