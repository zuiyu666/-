---
aliases: 
tags: 
width:
date created: 星期四, 十月 13日 2022, 1:29:56 下午
date modified: 星期二, 十月 18日 2022, 1:12:18 下午
---
UDEC Commands and FISH
Block
Block Commands
block apply command
block boundary-elements command
block cave command
block cell command
block change command
block config command
block contact commands
block contact add-dilation command
block contact change command
block contact cmodel command
block contact cy-substepping command
block contact delete-open command
block contact freeze-new command
block contact group command
block contact history command
block contact initialize command
block contact join command
block contact join-stiffness-normal command
block contact join-stiffness-shear command
block contact join-ratio command
block contact starting-id command
block contact length-miniumum command
block contact list command
block contact material-table command
block contact property command
block contact property material command
block contact reset command
block contact tolerance command
block corner command
block create command
block creep commands
block creep history command
block creep list command
block creep time-total command
block creep timestep command
block cut command
block cycle command
block delete command
block domain command
block dynamic commands
block edge commands
block edge apply command
block edge apply-interior command
block edge apply list command
block edge property command
block factor-of-safety command
block fix command
block fluid commands
block fluid aperture command
block fluid aperture-max-ratio command
block fluid aperture-minimum command
block fluid cavitation command
block fluid clear command
block fluid compressible command
block fluid crack-flow command
block fluid far-field command
block fluid fast-flow command
block fluid flow command
block fluid gasflow command
block fluid history command
block fluid incompressible command
block fluid list command
block fluid property command
block fluid steady-state command
block fluid timestep-mode command
block fluid two-phase command
block fragment-energy command
block free command
block giic command
block gridpoint commands
block gridpoint apply command
block gridpoint apply-interior command
block gridpoint thermal-apply command
block gridpoint free command
block gridpoint group command
block gridpoint history command
block gridpoint initialize command
block gridpoint list command
block gridpoint slave command
block gridpoint slave-negative command
block gridpoint trace command
block group command
block hide command
block history command
block insitu command
block join-block command
block join-contact command
block joint-delete command
block joint-region command
block large-strain command
block link command
block list command
block mechanical commands
block mechanical active command
block mechanical damping command
block mechanical deterministic command
block mechanical energy command
block mechanical gravity command
block mechanical history command
block mechanical mass-scale command
block mechanical multi-threading command
block mechanical reset command
block mechanical time command
block mechanical timestep-factor command
block property material command
block show command
block solve command
block structure commands
block structure beam command
block structure cable command
block structure liner command
block structure reinforcement command
block structure rockbolt command
block structure support command
block thermal commands
block thermal cycle command
block thermal history command
block thermal list command
block thermal property command
block thermal substep-mechanical command
block thermal substep-thermal command
block thermal tolerance-gridpoint command
block tolerance command
block trace position command
block zone commands
block zone cmodel command
block zone generate command
block zone group command
block zone history command
block zone initialize command
block zone list command
block zone nodal-mixed-discretization command
block zone property command
null model properties
elastic model properties
anisotropic model properties
drucker-prager model properties
mohr-coulomb model properties
ubiquitous-joint model properties
strain-softening model properties
softening-ubiquitous model properties
double-yield model properties
cam-clay model properties
chsoil model properties
cysoil model properties
hoek-brown-pac model properties
hoek-brown model properties
maxwell model properties
burgers model properties
power model properties
wipp model properties
burgers-mohr model properties
power-mohr model properties
wipp-drucker model properties
wipp-salt model properties
Block FISH Functions
block
block.area
block.bex
block.corner
block.densityscaling
block.extra
block.fix
block.force
Vector Access
Component Access
block.gp
block.group
block.head
block.hidden
block.load
Vector Access
Component Access
block.mass
block.mat
block.model
block.moi
block.moment
block.near
block.next
block.pos
Vector Access
Component Access
block.type
block.vel
Vector Access
Component Access
block.vel.rot
block.zone
block.boundary
block.boundary.force
Vector Access
Component Access
block.boundary.gp
block.boundary.head
block.boundary.history.address.x
block.boundary.history.address.y
block.boundary.increment
Vector Access
Component Access
block.boundary.internal.head
block.boundary.near
block.boundary.next
block.boundary.reaction.x
block.boundary.reaction.y
block.boundary.type.x
block.boundary.type.y
block.boundary.vel
Vector Access
Component Access
block.config
block.config.axisymmetry
block.config.cell
block.config.creep
block.config.fluid
block.config.pstress
block.config.thermal
block.contact
block.contact.block1
block.contact.block2
block.contact.cmodel
block.contact.force.normal
block.contact.disp.shear
block.contact.domain1
block.contact.domain2
block.contact.extension.pointer
block.contact.extra
block.contact.force.shear
block.contact.group
block.contact.head
block.contact.id
block.contact.model
block.contact.jointset.id
block.contact.length
block.contact.link1
block.contact.link2
block.contact.mat
block.contact.near
block.contact.next
block.contact.normal
Vector Access
Component Access
block.contact.obj.type
block.contact.pos
Vector Access
Component Access
block.contact.prop
block.contact.state
block.contact.thermal.source
block.contact.type
block.corner
block.corner.block
block.corner.boundary
block.corner.contact
block.corner.disp
Vector Access
Component Access
block.corner.extra
block.corner.gp
block.corner.group
block.corner.link
block.corner.link.reverse
block.corner.near
block.corner.next
block.corner.pos
Vector Access
Component Access
block.corner.vel
Vector Access
Component Access
block.creep
block.creep.time.total
block.creep.timestep
block.domain
block.domain.contact
block.domain.extra
block.domain.fix
block.domain.fix.nonwetting
block.domain.fluid.bulk
block.domain.fluid.density
block.domain.group
block.domain.head
block.domain.near
block.domain.next
block.domain.outer
block.domain.pos
Vector Access
Component Access
block.domain.pp
block.domain.pp.nonwetting
block.domain.saturation
block.domain.temp
block.domain.volume
block.fluid
block.fluid.bulk
block.fluid.density
block.fluid.time.total
block.force
Vector Access
Component Access
block.gridpoint
block.gp.block
block.gp.boundary.corner
block.gp.boundary.corner.make
block.gp.boundary.internal
block.gp.corner
block.gp.density.scaling
block.gp.disp
Vector Access
Component Access
block.gp.dynamic.mass
block.gp.extra
block.gp.force
Vector Access
Component Access
block.gp.group
block.gp.id
block.gp.mass
block.gp.near
block.gp.next
block.gp.pos
Vector Access
Component Access
block.gp.temp
block.gp.thermal.mass
block.gp.vel
Vector Access
Component Access
block.gp.reaction.x
block.gp.reaction.y
block.gp.thermal.source
block.thermal.source.corner
block.thermal.source.contact
block.thermal.source.decay
block.thermal.source.gridpoint
block.thermal.source.head
block.thermal.source.next
block.thermal.source.strength
block.thermal.source.time.thermal
block.thermal.source.type
block.load
Vector Access
Component Access
block.mechanical
block.mechanical.time.total
block.mechanical.timestep
block.pos
Vector Access
Component Access
block.structure
block.struct.beam
block.struct.beam.area
block.struct.beam.model
block.struct.beam.extra
block.struct.beam.force.axial
block.struct.beam.force.shear
block.struct.beam.group
block.struct.beam.head
block.struct.beam.id
block.struct.beam.length
block.struct.beam.mat
block.struct.beam.moi
block.struct.beam.moment1
block.struct.beam.moment2
block.struct.beam.next
block.struct.beam.node1
block.struct.beam.node2
block.struct.beam.pos
block.struct.beam.shape
block.struct.beam.state.axial
block.struct.beam.state.shear
block.struct.beam.stiff
block.struct.beam.thick
block.struct.beam.unit
block.struct.beam.node
block.struct.beam.node.disp
block.struct.beam.node.disp.rot
block.struct.beam.node.extra
block.struct.beam.node.force
block.struct.beam.node.force.apply
block.struct.beam.node.force.shear
block.struct.beam.node.group
block.struct.beam.node.head
block.struct.beam.node.id
block.struct.beam.node.layer
block.struct.beam.node.mass.grav
block.struct.beam.node.mass.scaled
block.struct.beam.node.mat
block.struct.beam.node.moi
block.struct.beam.node.moi.scaled
block.struct.beam.node.moment
block.struct.beam.node.moment.applied
block.struct.beam.node.next
block.struct.beam.node.pos
block.struct.beam.node.temperature.inc
block.struct.beam.node.unit
block.struct.beam.node.vel
block.struct.beam.node.vel.rot
block.struct.beam.node.zone
block.struct.beam.interface
block.struct.beam.interface.block
block.struct.beam.interface.disp.normal
block.struct.beam.interface.disp.shear
block.struct.beam.interface.extra
block.struct.beam.interface.force.normal
block.struct.beam.interface.force.shear
block.struct.beam.interface.group
block.st.beam.interface.head
block.struct.beam.interface.id
block.struct.beam.interface.link
block.struct.beam.interface.mat
block.struct.beam.interface.model
block.struct.beam.interface.next
block.struct.beam.interface.node
block.struct.beam.interface.pos
block.struct.beam.interface.shift
block.struct.beam.interface.state
block.struct.beam.interface.vel
block.struct.bolt
block.struct.bolt.area
block.struct.bolt.extra
block.struct.bolt.force.axial
block.struct.bolt.force.shear
block.struct.bolt.group
block.struct.bolt.head
block.struct.bolt.id
block.struct.bolt.length
block.struct.bolt.mat
block.struct.bolt.moi
block.struct.bolt.moment1
block.struct.bolt.moment2
block.struct.bolt.next
block.struct.bolt.node1
block.struct.bolt.node2
block.struct.bolt.pos
block.struct.bolt.state.axial
block.struct.bolt.state.shear
block.struct.bolt.stiff
block.struct.bolt.unit
block.struct.bolt.node
block.struct.bolt.node.couple.confine
block.struct.bolt.node.couple.disp.normal
block.struct.bolt.node.couple.disp.shear
block.struct.bolt.node.couple.force.normal
block.struct.bolt.node.couple.force.shear
block.struct.bolt.node.couple.gap
block.struct.bolt.node.state.normal
block.struct.bolt.node.disp
block.struct.bolt.node.disp.rot
block.struct.bolt.node.extra
block.struct.bolt.node.force
block.struct.bolt.node.force.apply
block.struct.bolt.node.force.shear
block.struct.bolt.node.group
block.struct.bolt.node.head
block.struct.bolt.node.id
block.struct.bolt.node.inside
block.struct.bolt.node.mass.grav
block.struct.bolt.node.mass.scaled
block.struct.bolt.node.mat
block.struct.bolt.node.moi
block.struct.bolt.node.moi.scaled
block.struct.bolt.node.moment
block.struct.bolt.node.moment.applied
block.struct.bolt.node.next
block.struct.bolt.node.pos
block.struct.bolt.node.state
block.struct.bolt.node.temperature.inc
block.struct.bolt.node.unit
block.struct.bolt.node.vel
block.struct.bolt.node.vel.rot
block.struct.bolt.node.zone
block.struct.bolt.node.next
block.struct.cable
block.struct.cable.area
block.struct.cable.cons
block.struct.cable.extra
block.struct.cable.force.axial
block.struct.cable.force.shear
block.struct.cable.group
block.struct.cable.id
block.struct.cable.length
block.struct.cable.mat
block.struct.cable.moi
block.struct.cable.force.moment1
block.struct.cable.force.moment2
block.struct.cable.next
block.struct.cable.node1
block.struct.cable.node2
block.struct.cable.pos
block.struct.cable.shape
block.struct.cable.state
block.struct.cable.stiff
block.struct.cable.strain
block.struct.cable.thick
block.struct.cable.unit
block.struct.cable.element.head
block.struct.cable.node
block.struct.cable.node.group
block.struct.cable.node.disp
block.struct.cable.node.extra
block.struct.cable.node.force
block.struct.cable.node.force.apply
block.struct.cable.node.force.shear
block.struct.cable.node.head
block.struct.cable.node.id
block.struct.cable.node.mass.grav
block.struct.cable.node.mass.scaled
block.struct.cable.node.mat
block.struct.cable.node.next
block.struct.cable.node.pos
block.struct.cable.node.state
block.struct.cable.node.unit
block.struct.cable.node.vel
block.struct.cable.node.zone
block.struct.liner
block.struct.liner.area
block.struct.liner.model
block.struct.liner.extra
block.struct.liner.force.axial
block.struct.liner.force.shear
block.struct.liner.group
block.struct.liner.head
block.struct.liner.id
block.struct.liner.length
block.struct.liner.mat
block.struct.liner.moi
block.struct.liner.moment1
block.struct.liner.moment2
block.struct.liner.next
block.struct.liner.node1
block.struct.liner.node2
block.struct.liner.pos
block.struct.liner.shape
block.struct.liner.state.axial
block.struct.liner.state.shear
block.struct.liner.stiff
block.struct.liner.thick
block.struct.liner.unit
block.struct.liner.node
block.struct.liner.node.disp
block.struct.liner.node.disp.rot
block.struct.liner.node.extra
block.struct.liner.node.force
block.struct.liner.node.force.apply
block.struct.liner.node.force.shear
block.struct.liner.node.group
block.struct.liner.node.head
block.struct.liner.node.id
block.struct.liner.node.layer
block.struct.liner.node.mass.grav
block.struct.liner.node.mass.scaled
block.struct.liner.node.mat
block.struct.liner.node.moi
block.struct.liner.node.moi.scaled
block.struct.liner.node.moment
block.struct.liner.node.moment.applied
block.struct.liner.node.next
block.struct.liner.node.pos
block.struct.liner.node.temperature.inc
block.struct.liner.node.unit
block.struct.liner.node.vel
block.struct.liner.node.vel.rot
block.struct.liner.node.zone
block.struct.liner.interface
block.struct.liner.interface.block
block.struct.liner.interface.disp.normal
block.struct.liner.interface.disp.shear
block.struct.liner.interface.extra
block.struct.liner.interface.force.normal
block.struct.liner.interface.force.shear
block.struct.liner.interface.group
block.struct.liner.interface.head
block.struct.liner.interface.id
block.struct.liner.interface.link
block.struct.liner.interface.mat
block.struct.liner.interface.model
block.struct.liner.interface.next
block.struct.liner.interface.node
block.struct.liner.interface.pos
block.struct.liner.interface.shift
block.struct.liner.interface.state
block.struct.liner.interface.vel
block.struct.reinf
block.struct.reinf.angle
block.struct.reinf.block1
block.struct.reinf.block2
block.struct.reinf.disp
block.struct.reinf.extra
block.struct.reinf.force.axial
block.struct.reinf.force.shear
block.struct.reinf.group
block.struct.reinf.head
block.struct.reinf.id
block.struct.reinf.force.joint.normal
block.struct.reinf.force.joint.shear
block.struct.reinf.mat
block.struct.reinf.next
block.struct.reinf.pos
block.struct.reinf.vel
block.struct.support
block.struct.support.bottom.block
block.struct.support.bottom.corner
block.struct.support.bottom.factor
block.struct.support.deleteflag
block.struct.support.disp.normal
block.struct.support.disp.shear
block.struct.support.extra
block.struct.support.force.normal
block.struct.support.force.shear
block.struct.support.group
block.struct.support.head
block.struct.support.id
block.struct.support.mat
block.struct.support.next
block.struct.support.sub.count
block.struct.support.sub.link
block.struct.support.top.block
block.struct.support.top.corner
block.struct.support.top.factor
block.struct.support.type
block.struct.support.unit
block.thermal
block.thermal.time.total
block.thermal.timestep
block.gp.thermal.source
block.thermal.source.corner
block.thermal.source.contact
block.thermal.source.decay
block.thermal.source.gridpoint
block.thermal.source.head
block.thermal.source.next
block.thermal.source.strength
block.thermal.source.time.thermal
block.thermal.source.type
block.vel
Vector Access
Component Access
block.zone
block.zone.area
block.zone.biot
block.zone.block
block.zone.bulk
block.zone.density
block.zone.extension.array
block.zone.extra
block.zone.strain.increment
block.zone.strain.rate
block.zone.gp
block.zone.group
block.zone.inside
block.zone.mass
block.zone.mat
block.zone.metric
block.zone.model
block.zone.near
block.zone.next
block.zone.pos
Vector Access
Component Access
block.zone.pp
block.zone.prop
block.zone.rotation
block.zone.shear
block.zone.state
block.zone.stress.xx
block.zone.stress.xy
block.zone.stress.yy
block.zone.stress.zz
block.zone.strain.total
global
cycle
fmem
fracb
fracz
gravity
Vector Access
Component Access
imem
junk
mfree
mtop
solve.force.balance
solve.force.magnitude
solve.ratio
solve.ratio.local
solve.ratio.maximum
step
unbalanced_force
xmem
prop
prop.block.bulk
prop.block.cohesion
prop.block.density
prop.block.dilation
prop.block.friction
prop.block.shear
prop.block.tension
prop.contact.cohesion
prop.contact.cohesion.residual
prop.contact.dilation
prop.contact.friction
prop.contact.friction.residual
prop.contact.stiffness.normal
prop.contact.stiffness.shear
prop.contact.tension
prop.contact.tension.residual
prop.reinf.axial.stiffness
prop.reinf.axial.stiffness.exp
prop.reinf.length
prop.reinf.reversal.factor
prop.reinf.shear.stiffness
prop.reinf.shear.stiffness.exp
prop.reinf.strain.exp
prop.reinf.yield.normal
prop.reinf.yield.shear