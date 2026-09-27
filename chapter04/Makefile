.PHONY: check syntax lint yaml inventory

PLAYBOOKS := $(wildcard playbooks/*.yml playbooks/*.yaml)
INVENTORY := inventory

GREEN  := \033[32m
YELLOW := \033[33m
BLUE   := \033[34m
RED    := \033[31m
RESET  := \033[0m
BOLD   := \033[1m

check: syntax lint yaml inventory
	@printf "\n$(GREEN)$(BOLD)✓ All checks passed!$(RESET)\n\n"

syntax:
	@printf "\n$(BLUE)$(BOLD)━━━ Ansible syntax check ━━━$(RESET)\n"
	@ansible-playbook --syntax-check $(PLAYBOOKS)
	@printf "$(GREEN)✓ Syntax OK$(RESET)\n"

lint:
	@printf "\n$(BLUE)$(BOLD)━━━ Ansible lint ━━━$(RESET)\n"
	@ansible-lint $(PLAYBOOKS)
	@printf "$(GREEN)✓ Ansible lint OK$(RESET)\n"

yaml:
	@printf "\n$(BLUE)$(BOLD)━━━ YAML lint ━━━$(RESET)\n"
	@yamllint $(PLAYBOOKS)
	@printf "$(GREEN)✓ YAML lint OK$(RESET)\n"

inventory:
	@printf "\n$(BLUE)$(BOLD)━━━ Ansible inventory ━━━$(RESET)\n"
	@ansible-inventory --list -i $(INVENTORY)
	@printf "$(GREEN)✓ Inventory OK$(RESET)\n"
