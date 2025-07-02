
# AI Domains Regex Patterns

This repository contains a comprehensive regex pattern for detecting AI and tech company domains based on their services domains.

## Regex Pattern

```regex
/.*(perplexity\.ai|you\.com|searchgpt\.com|chatgpt\.com|chat\.openai\.com|claude\.ai|anthropic\.com|gemini\.google\.com|bard\.google\.com|bing\.com.*chat|copilot\.microsoft\.com|phind\.com|kagi\.com|deepseek\.com|chat\.deepseek\.com|mistral\.ai|chat\.mistral\.ai|lechat\.mistral\.ai|cohere\.com|meta\.ai|groq\.com|together\.ai|fireworks\.ai|openrouter\.ai|grok\.x\.com|x\.com.*grok|pi\.ai|inflection\.ai|cerebras\.ai|openai\.com|google\.com.*bard|google\.com.*gemini|microsoft\.com.*copilot).*/i
```

## Pattern Breakdown

| Category | Company/Service | Effective Pattern | Example URLs |
|----------|-----------------|-------------------|--------------|
| AI Search | Perplexity | `.*perplexity\.ai.*` | https://perplexity.ai/search, https://sub.perplexity.ai |
| Search Engine | You.com | `.*you\.com.*` | https://you.com/search, https://api.you.com |
| AI Search | OpenAI | `.*searchgpt\.com.*` | https://searchgpt.com/chat, https://www.searchgpt.com |
| AI Assistant | OpenAI | `.*chatgpt\.com.*` | https://chatgpt.com/c/123, https://chatgpt.com/auth |
| AI Assistant | OpenAI | `.*chat\.openai\.com.*` | https://chat.openai.com/chat, https://chat.openai.com/auth |
| AI Assistant | Anthropic | `.*claude\.ai.*` | https://claude.ai/chat, https://claude.ai/login |
| AI Company | Anthropic | `.*anthropic\.com.*` | https://anthropic.com/claude, https://www.anthropic.com |
| AI Assistant | Google | `.*gemini\.google\.com.*` | https://gemini.google.com/app, https://gemini.google.com/chat |
| AI Assistant | Google | `.*bard\.google\.com.*` | https://bard.google.com/chat, https://bard.google.com/u/0 |
| AI Search | Microsoft | `.*bing\.com.*chat.*` | https://bing.com/chat, https://bing.com/search/chat/new |
| AI Assistant | Microsoft | `.*copilot\.microsoft\.com.*` | https://copilot.microsoft.com/chat, https://copilot.microsoft.com/auth |
| AI Search | Phind | `.*phind\.com.*` | https://phind.com/search, https://www.phind.com |
| Search Engine | Kagi | `.*kagi\.com.*` | https://kagi.com/search, https://kagi.com/login |
| AI Company | DeepSeek | `.*deepseek\.com.*` | https://deepseek.com/chat, https://www.deepseek.com |
| AI Assistant | DeepSeek | `.*chat\.deepseek\.com.*` | https://chat.deepseek.com/coder, https://chat.deepseek.com/auth |
| AI Company | Mistral AI | `.*mistral\.ai.*` | https://mistral.ai/chat, https://www.mistral.ai |
| AI Assistant | Mistral AI | `.*chat\.mistral\.ai.*` | https://chat.mistral.ai/chat, https://chat.mistral.ai/login |
| AI Assistant | Mistral AI | `.*lechat\.mistral\.ai.*` | https://lechat.mistral.ai/chat, https://lechat.mistral.ai/auth |
| AI Company | Cohere | `.*cohere\.com.*` | https://cohere.com/chat, https://dashboard.cohere.com |
| AI Assistant | Meta | `.*meta\.ai.*` | https://meta.ai/chat, https://www.meta.ai |
| AI Inference | Groq | `.*groq\.com.*` | https://groq.com/playground, https://console.groq.com |
| AI Platform | Together AI | `.*together\.ai.*` | https://together.ai/playground, https://api.together.ai |
| AI Platform | Fireworks AI | `.*fireworks\.ai.*` | https://fireworks.ai/models, https://app.fireworks.ai |
| AI Platform | OpenRouter | `.*openrouter\.ai.*` | https://openrouter.ai/playground, https://openrouter.ai/keys |
| AI Assistant | X (Twitter) | `.*grok\.x\.com.*` | https://grok.x.com/chat, https://grok.x.com/login |
| AI Assistant | X (Twitter) | `.*x\.com.*grok.*` | https://x.com/grok, https://x.com/i/grok/chat |
| AI Assistant | Inflection AI | `.*pi\.ai.*` | https://pi.ai/talk, https://www.pi.ai |
| AI Company | Inflection AI | `.*inflection\.ai.*` | https://inflection.ai/pi, https://www.inflection.ai |
| AI Hardware | Cerebras | `.*cerebras\.ai.*` | https://cerebras.ai/inference, https://www.cerebras.ai |
| AI Company | OpenAI | `.*openai\.com.*` | https://openai.com/chatgpt, https://platform.openai.com |
| AI Assistant | Google | `.*google\.com.*bard.*` | https://google.com/bard, https://google.com/ai/bard/chat |
| AI Assistant | Google | `.*google\.com.*gemini.*` | https://google.com/gemini, https://google.com/ai/gemini/app |
| AI Assistant | Microsoft | `.*microsoft\.com.*copilot.*` | https://microsoft.com/copilot, https://microsoft.com/ai/copilot/chat |

## Key Notes:
- The regex starts with `.*` which matches any characters before the domain
- All patterns will match the specified domain/subdomain plus any path that follows
- Patterns with `.*` in the middle (like `bing\.com.*chat`) match the domain followed by any characters, then the specified text
- The `i` flag makes the entire regex case-insensitive
- The "Effective Pattern" column shows how each individual pattern works within the full `.*(...).*/i` structure

## Logic
![image](https://github.com/user-attachments/assets/a0a497b5-7836-483c-9199-b0a5c2c8b824)


## Usage Examples

### JavaScript

```javascript
const aiDomainsRegex = /.*(perplexity\.ai|you\.com|searchgpt\.com|chatgpt\.com|chat\.openai\.com|claude\.ai|anthropic\.com|gemini\.google\.com|bard\.google\.com|bing\.com.*chat|copilot\.microsoft\.com|phind\.com|kagi\.com|deepseek\.com|chat\.deepseek\.com|mistral\.ai|chat\.mistral\.ai|lechat\.mistral\.ai|cohere\.com|meta\.ai|groq\.com|together\.ai|fireworks\.ai|openrouter\.ai|grok\.x\.com|x\.com.*grok|pi\.ai|inflection\.ai|cerebras\.ai|openai\.com|google\.com.*bard|google\.com.*gemini|microsoft\.com.*copilot).*/i;

// Test URLs
console.log(aiDomainsRegex.test('https://chat.openai.com/chat')); // true
console.log(aiDomainsRegex.test('https://claude.ai')); // true
console.log(aiDomainsRegex.test('https://bing.com/chat')); // true
console.log(aiDomainsRegex.test('https://example.com')); // false

// Extract matches
const url = 'https://chat.openai.com/chat';
const match = url.match(aiDomainsRegex);
console.log(match ? match[1] : 'No match'); // chat.openai.com
```

### Python

```python
import re

ai_domains_pattern = r'.*(perplexity\.ai|you\.com|searchgpt\.com|chatgpt\.com|chat\.openai\.com|claude\.ai|anthropic\.com|gemini\.google\.com|bard\.google\.com|bing\.com.*chat|copilot\.microsoft\.com|phind\.com|kagi\.com|deepseek\.com|chat\.deepseek\.com|mistral\.ai|chat\.mistral\.ai|lechat\.mistral\.ai|cohere\.com|meta\.ai|groq\.com|together\.ai|fireworks\.ai|openrouter\.ai|grok\.x\.com|x\.com.*grok|pi\.ai|inflection\.ai|cerebras\.ai|openai\.com|google\.com.*bard|google\.com.*gemini|microsoft\.com.*copilot).*'

ai_domains_regex = re.compile(ai_domains_pattern, re.IGNORECASE)

# Test URLs
test_urls = [
    'https://chat.openai.com/chat',
    'https://claude.ai', 
    'https://bing.com/chat',
    'https://example.com'
]

for url in test_urls:
    if ai_domains_regex.match(url):
        print(f"✓ {url} matches AI domain pattern")
    else:
        print(f"✗ {url} does not match")

# Extract AI domain from URL
def extract_ai_domain(url):
    match = ai_domains_regex.match(url)
    return match.group(1) if match else None

print(extract_ai_domain('https://chat.openai.com/chat'))  # chat.openai.com
```

### R

```r
library(stringr)

ai_domains_pattern <- ".*(perplexity\\.ai|you\\.com|searchgpt\\.com|chatgpt\\.com|chat\\.openai\\.com|claude\\.ai|anthropic\\.com|gemini\\.google\\.com|bard\\.google\\.com|bing\\.com.*chat|copilot\\.microsoft\\.com|phind\\.com|kagi\\.com|deepseek\\.com|chat\\.deepseek\\.com|mistral\\.ai|chat\\.mistral\\.ai|lechat\\.mistral\\.ai|cohere\\.com|meta\\.ai|groq\\.com|together\\.ai|fireworks\\.ai|openrouter\\.ai|grok\\.x\\.com|x\\.com.*grok|pi\\.ai|inflection\\.ai|cerebras\\.ai|openai\\.com|google\\.com.*bard|google\\.com.*gemini|microsoft\\.com.*copilot).*"

# Test URLs
test_urls <- c(
  "https://chat.openai.com/chat",
  "https://claude.ai",
  "https://bing.com/chat", 
  "https://example.com"
)

# Check matches
results <- str_detect(test_urls, regex(ai_domains_pattern, ignore_case = TRUE))
names(results) <- test_urls
print(results)

# Extract AI domains
extract_ai_domain <- function(url) {
  match <- str_match(url, regex(ai_domains_pattern, ignore_case = TRUE))
  return(match[2])
}

sapply(test_urls, extract_ai_domain)
```

### Java

```java
import java.util.regex.Pattern;
import java.util.regex.Matcher;

public class AIDomainMatcher {
    private static final String AI_DOMAINS_PATTERN = 
        ".*(perplexity\\.ai|you\\.com|searchgpt\\.com|chatgpt\\.com|chat\\.openai\\.com|claude\\.ai|anthropic\\.com|gemini\\.google\\.com|bard\\.google\\.com|bing\\.com.*chat|copilot\\.microsoft\\.com|phind\\.com|kagi\\.com|deepseek\\.com|chat\\.deepseek\\.com|mistral\\.ai|chat\\.mistral\\.ai|lechat\\.mistral\\.ai|cohere\\.com|meta\\.ai|groq\\.com|together\\.ai|fireworks\\.ai|openrouter\\.ai|grok\\.x\\.com|x\\.com.*grok|pi\\.ai|inflection\\.ai|cerebras\\.ai|openai\\.com|google\\.com.*bard|google\\.com.*gemini|microsoft\\.com.*copilot).*";
    
    private static final Pattern pattern = Pattern.compile(AI_DOMAINS_PATTERN, Pattern.CASE_INSENSITIVE);
    
    public static boolean isAIDomain(String url) {
        return pattern.matcher(url).matches();
    }
    
    public static String extractAIDomain(String url) {
        Matcher matcher = pattern.matcher(url);
        return matcher.matches() ? matcher.group(1) : null;
    }
    
    public static void main(String[] args) {
        String[] testUrls = {
            "https://chat.openai.com/chat",
            "https://claude.ai",
            "https://bing.com/chat",
            "https://example.com"
        };
        
        for (String url : testUrls) {
            System.out.println(url + " -> " + isAIDomain(url));
            System.out.println("Extracted: " + extractAIDomain(url));
        }
    }
}
```

### PHP

```php
<?php
$ai_domains_pattern = '/.*(perplexity\.ai|you\.com|searchgpt\.com|chatgpt\.com|chat\.openai\.com|claude\.ai|anthropic\.com|gemini\.google\.com|bard\.google\.com|bing\.com.*chat|copilot\.microsoft\.com|phind\.com|kagi\.com|deepseek\.com|chat\.deepseek\.com|mistral\.ai|chat\.mistral\.ai|lechat\.mistral\.ai|cohere\.com|meta\.ai|groq\.com|together\.ai|fireworks\.ai|openrouter\.ai|grok\.x\.com|x\.com.*grok|pi\.ai|inflection\.ai|cerebras\.ai|openai\.com|google\.com.*bard|google\.com.*gemini|microsoft\.com.*copilot).*/i';

$test_urls = [
    'https://chat.openai.com/chat',
    'https://claude.ai',
    'https://bing.com/chat',
    'https://example.com'
];

foreach ($test_urls as $url) {
    if (preg_match($ai_domains_pattern, $url, $matches)) {
        echo "✓ $url matches AI domain: {$matches[1]}\n";
    } else {
        echo "✗ $url does not match\n";
    }
}

function extractAIDomain($url) {
    global $ai_domains_pattern;
    return preg_match($ai_domains_pattern, $url, $matches) ? $matches[1] : null;
}
?>
```

### Go

```go
package main

import (
    "fmt"
    "regexp"
)

func main() {
    aiDomainsPattern := `(?i).*(perplexity\.ai|you\.com|searchgpt\.com|chatgpt\.com|chat\.openai\.com|claude\.ai|anthropic\.com|gemini\.google\.com|bard\.google\.com|bing\.com.*chat|copilot\.microsoft\.com|phind\.com|kagi\.com|deepseek\.com|chat\.deepseek\.com|mistral\.ai|chat\.mistral\.ai|lechat\.mistral\.ai|cohere\.com|meta\.ai|groq\.com|together\.ai|fireworks\.ai|openrouter\.ai|grok\.x\.com|x\.com.*grok|pi\.ai|inflection\.ai|cerebras\.ai|openai\.com|google\.com.*bard|google\.com.*gemini|microsoft\.com.*copilot).*`
    
    regex := regexp.MustCompile(aiDomainsPattern)
    
    testUrls := []string{
        "https://chat.openai.com/chat",
        "https://claude.ai",
        "https://bing.com/chat",
        "https://example.com",
    }
    
    for _, url := range testUrls {
        if regex.MatchString(url) {
            matches := regex.FindStringSubmatch(url)
            fmt.Printf("✓ %s matches AI domain: %s\n", url, matches[1])
        } else {
            fmt.Printf("✗ %s does not match\n", url)
        }
    }
}
```

### C#

```csharp
using System;
using System.Text.RegularExpressions;

class Program
{
    private static readonly string AiDomainsPattern = 
        @".*(perplexity\.ai|you\.com|searchgpt\.com|chatgpt\.com|chat\.openai\.com|claude\.ai|anthropic\.com|gemini\.google\.com|bard\.google\.com|bing\.com.*chat|copilot\.microsoft\.com|phind\.com|kagi\.com|deepseek\.com|chat\.deepseek\.com|mistral\.ai|chat\.mistral\.ai|lechat\.mistral\.ai|cohere\.com|meta\.ai|groq\.com|together\.ai|fireworks\.ai|openrouter\.ai|grok\.x\.com|x\.com.*grok|pi\.ai|inflection\.ai|cerebras\.ai|openai\.com|google\.com.*bard|google\.com.*gemini|microsoft\.com.*copilot).*";
    
    private static readonly Regex regex = new Regex(AiDomainsPattern, RegexOptions.IgnoreCase);
    
    static void Main()
    {
        string[] testUrls = {
            "https://chat.openai.com/chat",
            "https://claude.ai",
            "https://bing.com/chat",
            "https://example.com"
        };
        
        foreach (string url in testUrls)
        {
            Match match = regex.Match(url);
            if (match.Success)
            {
                Console.WriteLine($"✓ {url} matches AI domain: {match.Groups[1].Value}");
            }
            else
            {
                Console.WriteLine($"✗ {url} does not match");
            }
        }
    }
}
```

## Categories Summary

- **AI Assistants**: 12 patterns
- **AI Companies**: 8 patterns  
- **Search Engines**: 3 patterns
- **AI Platforms**: 4 patterns
- **AI Hardware**: 1 pattern
- **AI Inference**: 1 pattern

**Total**: 32 unique patterns covering major AI and tech domains
