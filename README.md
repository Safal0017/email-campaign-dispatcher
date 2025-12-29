# 🚀 Email Campaign Dispatcher

**Built entirely for learning purposes** - Demonstrates Go **producer-consumer pattern** using **goroutines** and **unbuffered channels** for concurrent email dispatching.

## Overview
Reads recipients from `emails.csv`, uses **producer goroutines** to parse data into unbuffered channels, and multiple **consumer goroutines** to listen to the data from the producer via channel, render HTML email templates and send via SMTP to Mailpit.

CSV → Producers (goroutines) → Unbuffered Channel → Consumers → SMTP (Mailpit)

## Features
- **Goroutine concurrency** for producers and consumers
- **Unbuffered channels** for strict synchronization
- **WaitGroups** for proper coordination
- **SMTP integration** with Mailpit
- **HTML email templates** with `html/template`
- **CSV parsing** for recipient data

## Quick Start

1. **Start Mailpit** (email catcher):
docker run -d --name=mailpit -p 8025:8025 -p 1025:1025 axllent/mailpit

[Open UI → http://localhost:8025](http://localhost:8025)

2. **Run dispatcher**:
go run .


3. **Watch emails arrive** in Mailpit UI!

## Project Structure
├── main.go # Orchestrates producers/consumers + WaitGroups
├── producer.go # CSV parsing → unbuffered channel
├── consumer.go # Template rendering + SMTP sending
├── email.tmpl # HTML email template
├── emails.csv # Recipient data
├── go.mod # Go modules
└── info.md # Docker setup


## Learning Outcomes ✅
- Goroutine concurrency & synchronization
- Unbuffered channels (producer-consumer pattern)
- WaitGroups for graceful completion
- HTML template engine
- SMTP email integration
- Docker for local testing

## Acknowledgments 🙏
- **CodersGyan** - Original project inspiration
- **Mailpit** - Local SMTP testing tool
- **Go Community** - Concurrency primitives

---
*Made with ❤️ for Go learning*
