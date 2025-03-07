# Changelog

## 1.0.6 - 2025-03-07 - @0xnu
Refinements:
* Code scanning improvements
* Bug fixes

## 1.0.5 - 2025-03-05 - @0xnu
New Features:
* Document Export Capabilities for Code Reviews
  - Added PDF export with '--pdf' flag
  - Added HTML export with '--html' flag
  - Improved formatting and styling of exported files

## 1.0.4 - 2025-02-27 - @0xnu
Enhancements:
* Expanded LLM Support
  - Added Grok-2 integration with '--llm grok2' flag
  - Added Mixtral integration with '--llm mixtral' flag
  - Improved response handling and error recovery
  - Enhanced multi-model compatibility

* Enhanced Security Features
  - Advanced vulnerability detection and analysis
  - Improved security-focused code reviews
  - Real-time security pattern recognition
  - Detailed dependency scanning

## 1.0.3 - 2025-02-25 - @0xnu
Enhancements:
* Added code review functionality
  - Full codebase analysis with '--cb' flag
  - Single file review with '--sf' flag
  - Customizable focus areas (security, performance, concurrency, etc.)
  - Configurable severity levels (low, medium, high)
  - Custom output directory support with '--review-output'

* Enhanced LLM Integration
  - Improved accuracy and reliability
  - Optimized prompts for code analysis
  - Enhanced response parsing for better accuracy

* Expanded Language Support
  - Added support for 30+ programming languages
  - Auto-detection of programming languages
  - Natural language detection for code comments
  - Improved multi-language codebase handling

* Code Analysis Features
  - Security vulnerability detection
  - Performance bottleneck identification
  - Concurrency issue analysis
  - Dead code detection
  - Corner and edge case identification
  - Algorithmic efficiency analysis

## 1.0.2 - 2025-02-25 - @0xnu
* Added OpenAI integration as alternative LLM option
* Implemented LLM selection with `--llm` flag (claude|openai)
* Enhanced environment configuration to support multiple API keys
* Improved documentation with dual LLM usage examples

## 1.0.1 - 2025-02-25 - @0xnu
* Smart content size management with self-adjusting limits
* Intelligent file scanning with hidden file exclusion
* Advanced context building with automatic content truncation

## 1.0.0 - 2025-02-23 - @0xnu
* Initial release