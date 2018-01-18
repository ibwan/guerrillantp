# GuerrillaNtp #

GuerrillaNtp is a simple NTP (SNTP) client written in C# that can be embedded in desktop .NET applications
to provide them with accurate network time even when the system clock is unsynchronized.

```csharp
// perform only one query to get the offset
TimeSpan offset;
using (var ntp = new NtpClient(Dns.GetHostAddresses("pool.ntp.org")[0]))
{
    ntp.Timeout = TimeSpan.FromSeconds(5);
    var response = ntp.Query();
    offset = response.CorrectionOffset;
}
// use the offset throughout your app
var accurateTime = DateTime.UtcNow + offset;
```

* [Homepage](https://guerrillantp.machinezoo.com/) - Overview, download, tutorial, alternatives, contact.
* [Sources](https://bitbucket.org/robertvazan/guerrillantp/src) - Primary repository, preferred for pull requests.
* [License](https://www.apache.org/licenses/LICENSE-2.0) - Distributed under Apache License 2.0.

