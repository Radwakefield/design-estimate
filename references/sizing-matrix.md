# Sizing matrix

Source: Figma "Design Project T-shirt Sizing" (file McyWz18v4CJHiFJZbXI7MJ, node 62:45).

## Inputs (drive the size)

| Dimension | Small | Medium | Large | X-Large |
|---|---|---|---|---|
| **Impact** | Lights-on / small KR / follow-on to larger work | Small KR impact projected | Med-high OKR impact, experimentation may be required | High OKR impact, experimentation required |
| **Scope** | Single feature, single surface, single audience, <=1 stakeholder team | Multiple features across 1-2 surfaces, single audience, updates to existing components, 1-2 stakeholders | Multiple features across several surfaces, some new components, 2+ stakeholder teams | Multiple features across multiple surfaces, multiple audiences, several new components, 2+ teams |
| **Discovery (ambiguity)** | Low ambiguity, existing insights, clear solution | Some ambiguity, existing insights, clear options | Ambiguous, needs new insights, some novelty | Highly ambiguous, low definition, significant new insights + novel solution |

## Size -> duration + outputs

| Size | Duration | Research | Exploration & refinement | Feedback cycles | Project plan |
|---|---|---|---|---|---|
| **Small** | Days-1 wk | None | Single feature, no DS updates, limited QA | Async crit & review | Explore -> Critique (async) -> Refine (async) |
| **Medium** | 2-3 wks | Validation only | Multi-feature/flow, DS updates maybe, no new components, some QA | Live crit & review (>=1 each) | Explore -> Critique -> Validation UXR -> Refine -> Review |
| **Large** | 4-5 wks | Discovery + validation | End-to-end flows, IA + DS + new components, significant QA | Live crit after explore AND after validation/refine | Discovery UXR -> Explore -> Crit 1 -> Review 1 -> Refine -> Validation UXR -> Refine -> Crit 2 -> Review 2 -> Refine |
| **X-Large** | 6-8 wks | Break into smaller bodies of work | - | - | - |
| **Custom** | 8+ wks | Custom | - | - | TBD |

## Size-resolution rule
1. Read each dimension (Impact / Scope / Discovery) to a size independently.
2. **Base size = the highest of the three reads** (scope/ambiguity rarely shrink).
3. **Disagreement flag:** if the three reads span MORE than one size (e.g. Small + Large),
   lower confidence and trigger the interview for the straddling dimension(s) before locking.
4. **New-component modifier:** a single new component is NOT an automatic Large. Treat
   new-component COUNT as a modifier - one new component on an otherwise-contained project
   reads Medium; multiple new components / a new component system pushes toward Large.

## Standing rules
- **X-Large -> recommend splitting** with product into smaller projects. Do not produce a plan.
- **Custom (8+ wks, fundamentally novel)** -> flag for custom sizing (e.g. EAP AI Project).

## Example project mapping (for calibration)
- Small: SSIP M1 - Directory
- Medium: Provider expertise, H2R DBT Improvements, Reg: Complete intake flow
- Large: Time-based therapy, Psych migration
- X-Large: MIC completion, Provider Bookability, Treatment Plans, Patient Referral Program
- Custom: EAP AI Project
