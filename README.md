
# AI Domains Regex Patterns

This repository contains a comprehensive regex pattern for detecting AI and tech company domains based on their services domains.

## Regex Pattern

```regex
/.*(perplexity\.ai|you\.com|searchgpt\.com|chatgpt\.com|chat\.openai\.com|claude\.ai|anthropic\.com|gemini\.google\.com|bard\.google\.com|bing\.com.*chat|copilot\.microsoft\.com|phind\.com|kagi\.com|deepseek\.com|chat\.deepseek\.com|mistral\.ai|chat\.mistral\.ai|lechat\.mistral\.ai|cohere\.com|meta\.ai|groq\.com|together\.ai|fireworks\.ai|openrouter\.ai|grok\.x\.com|x\.com.*grok|pi\.ai|inflection\.ai|cerebras\.ai|openai\.com|google\.com.*bard|google\.com.*gemini|microsoft\.com.*copilot).*/i
```

## Pattern Breakdown

| Regex Pattern | Category | Company/Service | Match Type | Example URLs |
|---------------|----------|-----------------|------------|--------------|
| `perplexity\.ai` | AI Search | Perplexity | Exact domain | perplexity.ai |
| `you\.com` | Search Engine | You.com | Exact domain | you.com |
| `searchgpt\.com` | AI Search | OpenAI | Exact domain | searchgpt.com |
| `chatgpt\.com` | AI Assistant | OpenAI | Exact domain | chatgpt.com |
| `chat\.openai\.com` | AI Assistant | OpenAI | Subdomain | chat.openai.com |
| `claude\.ai` | AI Assistant | Anthropic | Exact domain | claude.ai |
| `anthropic\.com` | AI Company | Anthropic | Exact domain | anthropic.com |
| `gemini\.google\.com` | AI Assistant | Google | Subdomain | gemini.google.com |
| `bard\.google\.com` | AI Assistant | Google | Subdomain | bard.google.com |
| `bing\.com.*chat` | AI Search | Microsoft | Wildcard path | bing.com/chat, bing.com/search/chat |
| `copilot\.microsoft\.com` | AI Assistant | Microsoft | Subdomain | copilot.microsoft.com |
| `phind\.com` | AI Search | Phind | Exact domain | phind.com |
| `kagi\.com` | Search Engine | Kagi | Exact domain | kagi.com |
| `deepseek\.com` | AI Company | DeepSeek | Exact domain | deepseek.com |
| `chat\.deepseek\.com` | AI Assistant | DeepSeek | Subdomain | chat.deepseek.com |
| `mistral\.ai` | AI Company | Mistral AI | Exact domain | mistral.ai |
| `chat\.mistral\.ai` | AI Assistant | Mistral AI | Subdomain | chat.mistral.ai |
| `lechat\.mistral\.ai` | AI Assistant | Mistral AI | Subdomain | lechat.mistral.ai |
| `cohere\.com` | AI Company | Cohere | Exact domain | cohere.com |
| `meta\.ai` | AI Assistant | Meta | Exact domain | meta.ai |
| `groq\.com` | AI Inference | Groq | Exact domain | groq.com |
| `together\.ai` | AI Platform | Together AI | Exact domain | together.ai |
| `fireworks\.ai` | AI Platform | Fireworks AI | Exact domain | fireworks.ai |
| `openrouter\.ai` | AI Platform | OpenRouter | Exact domain | openrouter.ai |
| `grok\.x\.com` | AI Assistant | X (Twitter) | Subdomain | grok.x.com |
| `x\.com.*grok` | AI Assistant | X (Twitter) | Wildcard path | x.com/grok, x.com/i/grok |
| `pi\.ai` | AI Assistant | Inflection AI | Exact domain | pi.ai |
| `inflection\.ai` | AI Company | Inflection AI | Exact domain | inflection.ai |
| `cerebras\.ai` | AI Hardware | Cerebras | Exact domain | cerebras.ai |
| `openai\.com` | AI Company | OpenAI | Exact domain | openai.com |
| `google\.com.*bard` | AI Assistant | Google | Wildcard path | google.com/bard, google.com/ai/bard |
| `google\.com.*gemini` | AI Assistant | Google | Wildcard path | google.com/gemini, google.com/ai/gemini |
| `microsoft\.com.*copilot` | AI Assistant | Microsoft | Wildcard path | microsoft.com/copilot, microsoft.com/ai/copilot |

## Pattern Features

- **Case Insensitive**: The `i` flag makes the pattern case-insensitive
- **Anchored**: `.*` at the beginning and end allows matching within larger URLs
- **Escaped Dots**: Domain dots are properly escaped with `\.`
- **Wildcard Paths**: Some patterns use `.*` to match various paths within domains

## Logic
![image](https://github.com/user-attachments/assets/8980c0f7-1183-403d-9162-4019b2cf3318)

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
