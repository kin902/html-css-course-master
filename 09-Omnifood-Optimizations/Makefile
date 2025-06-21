# Omnifood Makefile for SCSS compilation
# Author: Vinh

# Directories
SCSS_DIR = scss
CSS_DIR = css
SCSS_MAIN = $(SCSS_DIR)/main.scss
CSS_OUTPUT = $(CSS_DIR)/output.css

# Default target
.PHONY: all watch build build-prod clean help
all: build

# Watch SCSS files for changes and compile
watch:
	@echo "Watching SCSS files for changes..."
	@sass --watch $(SCSS_MAIN):$(CSS_OUTPUT) --style expanded

# Build CSS for development (expanded with source maps)
build:
	@echo "Building CSS for development..."
	@sass $(SCSS_MAIN):$(CSS_OUTPUT) --style expanded --source-map

# Build CSS for production (compressed, no source maps)
build-prod:
	@echo "Building CSS for production..."
	@sass $(SCSS_MAIN):$(CSS_OUTPUT) --style compressed --no-source-map

# Clean generated CSS files
clean:
	@echo "Cleaning generated CSS files..."
	@rm -f $(CSS_OUTPUT) $(CSS_OUTPUT).map

# Help command
help:
	@echo "Omnifood SCSS Makefile"
	@echo ""
	@echo "Available commands:"
	@echo "  make all        - Default target, equivalent to 'make build'"
	@echo "  make watch      - Watch SCSS files for changes and compile in real-time"
	@echo "                    Uses expanded style with source maps for debugging"
	@echo "  make build      - Build CSS for development environment"
	@echo "                    Uses expanded style with source maps for better debugging"
	@echo "  make build-prod - Build CSS for production environment"
	@echo "                    Uses compressed style without source maps for optimal performance"
	@echo "  make clean      - Remove all generated CSS files and source maps"
	@echo "                    Deletes $(CSS_OUTPUT) and $(CSS_OUTPUT).map"
	@echo "  make help       - Display this detailed help message"
	@echo ""
	@echo "Configuration:"
	@echo "  SCSS_DIR     = $(SCSS_DIR)    (SCSS source directory)"
	@echo "  CSS_DIR      = $(CSS_DIR)     (CSS output directory)"
	@echo "  SCSS_MAIN    = $(SCSS_MAIN)   (Main SCSS file)"
	@echo "  CSS_OUTPUT   = $(CSS_OUTPUT)  (Output CSS file)"
