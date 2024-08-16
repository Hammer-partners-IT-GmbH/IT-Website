<script lang="ts">
	import { faArrowDownLong } from '@fortawesome/free-solid-svg-icons';
	import Fa from 'svelte-fa';

	type Team = {
		name: string;
		img: string;
	};

	let choice_string: string = 'praxis';

	function choice(type: string) {
		choice_string = type;
		const all_list = document.querySelectorAll('.auswahl ul li button');
		all_list.forEach((element) => {
			element.classList.remove('active');
		});
		const elemnt = document.getElementById(type);
		elemnt?.classList.toggle('active');
		return choice_string;
	}

	let team: Team[] = [
		{
			name: 'Dominik Schmerberg',
			img: '/img/dominik_schmerberg.jpg'
		},
		{
			name: 'Sascha Gerden',
			img: '/img/sascha_gerden.jpg'
		}
	];
</script>

<div class="nav">
	<div class="scroll">
		<a href="#digitale-loesungen">
			<Fa icon={faArrowDownLong}></Fa>
			<span class="visually-hidden">scroll down</span>
		</a>
	</div>
	<ul class="nav-list">
		<li><a href="#digitale-loesungen">Digitale Lösungen</a></li>
		<li><a href="#hastratus">Hastratus</a></li>
		<li><a href="#ansprechpartner">Ansprechpartner</a></li>
	</ul>
</div>

<div id="digitale-loesungen">
	<h2><strong>INTELLIGENTER</strong> IN DIE DIGITALE ÄRA</h2>
	<p>
		Mit digitalen Lösungen, die wir auf Ihre Abläufe anpassen, gewinnen Sie Zeit für das
		Kerngeschäft. Sie behalten den Überblick über Ihre Leistungsdaten und sind besser gewappnet für
		unternehmerische Entscheidungen.
	</p>
	<p>
		Wir bereiten die Zahlen Ihres Unternehmens digital auf. Wir stellen Ihnen Ihre Unternehmensdaten
		anschaulich zur Verfügung. Alles was für Sie steuerungsrelevant ist, erhalten Sie auf einen
		Blick. Unsere Lösungen sind cloudbasiert.
	</p>
</div>

<div id="hastratus" class="hastratus">
	<div class="info">
		<div class="content">
			<h2>HASTRATUS</h2>
			<b>INDIVIDUELLE LÖSUNGEN FÜR SIE</b>
			<p>
				Erhalten Sie eine Sofort-Analyse Ihrer Daten mit Hastratus, so heißt unser besonderes
				Reporting-System. Damit haben Sie ein individuelles digitales Werkzeug zur Hand - angepasst
				auf Ihre Abläufe, schnell und zeitsparend.
			</p>
			<ul>
				<li>Prozessberatung / Management-Informationssysteme</li>
				<li>Wirtschaftsprüfung durch IT-gestützte Daten- und Prozessanalyse</li>
				<li>Datenmigration</li>
			</ul>
		</div>
		<div class="image">
			<figure>
				<picture>
					<source
						srcset="https://hammer.partners/assets/images/c/img-03-0084a109.webp 1x, https://hammer.partners/assets/images/1/img-03-d03e8a63.webp 2x"
						type="image/webp"
					/>
					<img
						src="https://hammer.partners/assets/images/e/img-03-822ad54f.png"
						srcset="https://hammer.partners/assets/images/e/img-03-822ad54f.png 1x, https://hammer.partners/assets/images/c/img-03-f4c7f8de.png 2x"
						alt=""
						loading="lazy"
					/>
				</picture>
			</figure>
		</div>
	</div>

	<div
		id="prozessberatung_management-informationssysteme"
		class="prozessberatung_management-informationssysteme"
	>
		<h3>PROZESSBERATUNG / MANAGEMENT-INFORMATIONSSYSTEME</h3>
		<ul>
			<li>
				Potentiale zur Optimierung von Geschäftsprozessen aufdecken - mit Datenanalysen auf Basis
				der GdPDU-Daten der Finanzbuchhaltung und relevanter Vorsysteme
			</li>
			<li>
				Integriertes Datenmodell erstellen – mit individuellen Reports und Dashboards auf Basis von
				Microsoft Power BI
			</li>
		</ul>
	</div>

	<div
		id="wirtschaftsprüfung_durch_edv_gestützte_daten-_und_prozessanalyse"
		class="wirtschaftsprüfung_durch_edv_gestützte_daten-_und_prozessanalyse"
	>
		<h3>WIRTSCHAFTSPRÜFUNG DURCH EDV GESTÜTZTE DATEN- UND PROZESSANALYSE</h3>
		<ul>
			<li>
				Integrierte Datenmodelle erstellen – für die vollständig automatisierte Abstimmung der
				Finanzbuchhaltung mit Vorsystemen (zum Beispiel Materialwirtschaft, Personalwirtschaft,
				Anlagenverwaltung)
			</li>
			<li>
				Prozessanalyse auf Basis des erstellten Finanzdatenmodells - Analyse der Buchungen nach
				Datenherkunft, Benutzer, Zeitpunkt der Datenerfassung, Gegenkontenanalysen
			</li>
			<li>
				Die erstellten Datenmodelle sind die Basis eines Management-Informationssystems. Nutzen Sie
				unsere Abschlussprüfung als echten Mehrwert
			</li>
		</ul>
	</div>

	<div id="datenmigration" class="datenmigration">
		<h3>DATENMIGRATION</h3>
		<ul>
			<li>Entwicklung oder Prüfung von Migrationskonzepten</li>
			<li>
				Aus verschiedenen Teilsystemen – zum Beispiel automatisierte Abstimmung Materialwirtschaft
				mit Finanzbuchhaltung – erfolgt eine Konsistenzprüfung der Übernahmedaten (Stamm- und
				Bewegungsdaten)
			</li>
			<li>Erstellung validierter Datensätze für die Übernahme in das neue EDV-System</li>
		</ul>
	</div>
</div>

<div class="auswahl">
	<ul>
		<li><button id="praxis" class="active" on:click={() => choice('praxis')}>Praxis</button></li>
		<li><button id="krankenhaus" on:click={() => choice('krankenhaus')}>Krankenhaus</button></li>
		<li>
			<button id="nicht-medizinisch" on:click={() => choice('nicht-medizinisch')}
				>Nicht Medizinisch</button
			>
		</li>
	</ul>

	{#if choice_string === 'praxis'}
		<h2>PRAXIS</h2>
		<div>
			Lorem ipsum dolor sit amet consectetur adipisicing elit. Accusamus tempore ipsam reprehenderit
			beatae totam quas enim iste omnis quibusdam, fuga at, rem vero quisquam! Sapiente quos fugit
			atque saepe eius. Lorem ipsum dolor sit amet consectetur adipisicing elit. Accusamus tempore
			ipsam reprehenderit beatae totam quas enim iste omnis quibusdam, fuga at, rem vero quisquam!
			Sapiente quos fugit atque saepe eius.Lorem ipsum dolor sit amet consectetur adipisicing elit.
			Accusamus tempore ipsam reprehenderit beatae totam quas enim iste omnis quibusdam, fuga at,
			rem vero quisquam! Sapiente quos fugit atque saepe eius.Lorem ipsum dolor sit amet consectetur
			adipisicing elit. Accusamus tempore ipsam reprehenderit beatae totam quas enim iste omnis
			quibusdam, fuga at, rem vero quisquam! Sapiente quos fugit atque saepe eius.Lorem ipsum dolor
			sit amet consectetur adipisicing elit. Accusamus tempore ipsam reprehenderit beatae totam quas
			enim iste omnis quibusdam, fuga at, rem vero quisquam! Sapiente quos fugit atque saepe
			eius.Lorem ipsum dolor sit amet consectetur adipisicing elit. Accusamus tempore ipsam
			reprehenderit beatae totam quas enim iste omnis quibusdam, fuga at, rem vero quisquam!
			Sapiente quos fugit atque saepe eius.Lorem ipsum dolor sit amet consectetur adipisicing elit.
			Accusamus tempore ipsam reprehenderit beatae totam quas enim iste omnis quibusdam, fuga at,
			rem vero quisquam! Sapiente quos fugit atque saepe eius.Lorem ipsum dolor sit amet consectetur
			adipisicing elit. Accusamus tempore ipsam reprehenderit beatae totam quas enim iste omnis
			quibusdam, fuga at, rem vero quisquam! Sapiente quos fugit atque saepe eius.Lorem ipsum dolor
			sit amet consectetur adipisicing elit. Accusamus tempore ipsam reprehenderit beatae totam quas
			enim iste omnis quibusdam, fuga at, rem vero quisquam! Sapiente quos fugit atque saepe
			eius.Lorem ipsum dolor sit amet consectetur adipisicing elit. Accusamus tempore ipsam
			reprehenderit beatae totam quas enim iste omnis quibusdam, fuga at, rem vero quisquam!
			Sapiente quos fugit atque saepe eius.Lorem ipsum dolor sit amet consectetur adipisicing elit.
			Accusamus tempore ipsam reprehenderit beatae totam quas enim iste omnis quibusdam, fuga at,
			rem vero quisquam! Sapiente quos fugit atque saepe eius.Lorem ipsum dolor sit amet consectetur
			adipisicing elit. Accusamus tempore ipsam reprehenderit beatae totam quas enim iste omnis
			quibusdam, fuga at, rem vero quisquam! Sapiente quos fugit atque saepe eius.Lorem ipsum dolor
			sit amet consectetur adipisicing elit. Accusamus tempore ipsam reprehenderit beatae totam quas
			enim iste omnis quibusdam, fuga at, rem vero quisquam! Sapiente quos fugit atque saepe eius.
		</div>
	{:else if choice_string === 'krankenhaus'}
		<h2>KRANKENHAUS</h2>
		<div>
			Lorem ipsum dolor sit amet consectetur adipisicing elit. Accusamus tempore ipsam reprehenderit
			beatae totam quas enim iste omnis quibusdam, fuga at, rem vero quisquam! Sapiente quos fugit
			atque saepe eius. Lorem ipsum dolor sit amet consectetur adipisicing elit. Accusamus tempore
			ipsam reprehenderit beatae totam quas enim iste omnis quibusdam, fuga at, rem vero quisquam!
			Sapiente quos fugit atque saepe eius.Lorem ipsum dolor sit amet consectetur adipisicing elit.
			Accusamus tempore ipsam reprehenderit beatae totam quas enim iste omnis quibusdam, fuga at,
			rem vero quisquam! Sapiente quos fugit atque saepe eius.Lorem ipsum dolor sit amet consectetur
			adipisicing elit. Accusamus tempore ipsam reprehenderit beatae totam quas enim iste omnis
			quibusdam, fuga at, rem vero quisquam! Sapiente quos fugit atque saepe eius.Lorem ipsum dolor
			sit amet consectetur adipisicing elit. Accusamus tempore ipsam reprehenderit beatae totam quas
			enim iste omnis quibusdam, fuga at, rem vero quisquam! Sapiente quos fugit atque saepe
			eius.Lorem ipsum dolor sit amet consectetur adipisicing elit. Accusamus tempore ipsam
			reprehenderit beatae totam quas enim iste omnis quibusdam, fuga at, rem vero quisquam!
			Sapiente quos fugit atque saepe eius.Lorem ipsum dolor sit amet consectetur adipisicing elit.
			Accusamus tempore ipsam reprehenderit beatae totam quas enim iste omnis quibusdam, fuga at,
			rem vero quisquam! Sapiente quos fugit atque saepe eius.Lorem ipsum dolor sit amet consectetur
			adipisicing elit. Accusamus tempore ipsam reprehenderit beatae totam quas enim iste omnis
			quibusdam, fuga at, rem vero quisquam! Sapiente quos fugit atque saepe eius.Lorem ipsum dolor
			sit amet consectetur adipisicing elit. Accusamus tempore ipsam reprehenderit beatae totam quas
			enim iste omnis quibusdam, fuga at, rem vero quisquam! Sapiente quos fugit atque saepe
			eius.Lorem ipsum dolor sit amet consectetur adipisicing elit. Accusamus tempore ipsam
			reprehenderit beatae totam quas enim iste omnis quibusdam, fuga at, rem vero quisquam!
			Sapiente quos fugit atque saepe eius.Lorem ipsum dolor sit amet consectetur adipisicing elit.
			Accusamus tempore ipsam reprehenderit beatae totam quas enim iste omnis quibusdam, fuga at,
			rem vero quisquam! Sapiente quos fugit atque saepe eius.Lorem ipsum dolor sit amet consectetur
			adipisicing elit. Accusamus tempore ipsam reprehenderit beatae totam quas enim iste omnis
			quibusdam, fuga at, rem vero quisquam! Sapiente quos fugit atque saepe eius.Lorem ipsum dolor
			sit amet consectetur adipisicing elit. Accusamus tempore ipsam reprehenderit beatae totam quas
			enim iste omnis quibusdam, fuga at, rem vero quisquam! Sapiente quos fugit atque saepe eius.
		</div>
	{:else if choice_string === 'nicht-medizinisch'}
		<h2>NICHT MEDIZINISCH</h2>
		<div>
			Lorem ipsum dolor sit amet consectetur adipisicing elit. Accusamus tempore ipsam reprehenderit
			beatae totam quas enim iste omnis quibusdam, fuga at, rem vero quisquam! Sapiente quos fugit
			atque saepe eius. Lorem ipsum dolor sit amet consectetur adipisicing elit. Accusamus tempore
			ipsam reprehenderit beatae totam quas enim iste omnis quibusdam, fuga at, rem vero quisquam!
			Sapiente quos fugit atque saepe eius.Lorem ipsum dolor sit amet consectetur adipisicing elit.
			Accusamus tempore ipsam reprehenderit beatae totam quas enim iste omnis quibusdam, fuga at,
			rem vero quisquam! Sapiente quos fugit atque saepe eius.Lorem ipsum dolor sit amet consectetur
			adipisicing elit. Accusamus tempore ipsam reprehenderit beatae totam quas enim iste omnis
			quibusdam, fuga at, rem vero quisquam! Sapiente quos fugit atque saepe eius.Lorem ipsum dolor
			sit amet consectetur adipisicing elit. Accusamus tempore ipsam reprehenderit beatae totam quas
			enim iste omnis quibusdam, fuga at, rem vero quisquam! Sapiente quos fugit atque saepe
			eius.Lorem ipsum dolor sit amet consectetur adipisicing elit. Accusamus tempore ipsam
			reprehenderit beatae totam quas enim iste omnis quibusdam, fuga at, rem vero quisquam!
			Sapiente quos fugit atque saepe eius.Lorem ipsum dolor sit amet consectetur adipisicing elit.
			Accusamus tempore ipsam reprehenderit beatae totam quas enim iste omnis quibusdam, fuga at,
			rem vero quisquam! Sapiente quos fugit atque saepe eius.Lorem ipsum dolor sit amet consectetur
			adipisicing elit. Accusamus tempore ipsam reprehenderit beatae totam quas enim iste omnis
			quibusdam, fuga at, rem vero quisquam! Sapiente quos fugit atque saepe eius.Lorem ipsum dolor
			sit amet consectetur adipisicing elit. Accusamus tempore ipsam reprehenderit beatae totam quas
			enim iste omnis quibusdam, fuga at, rem vero quisquam! Sapiente quos fugit atque saepe
			eius.Lorem ipsum dolor sit amet consectetur adipisicing elit. Accusamus tempore ipsam
			reprehenderit beatae totam quas enim iste omnis quibusdam, fuga at, rem vero quisquam!
			Sapiente quos fugit atque saepe eius.Lorem ipsum dolor sit amet consectetur adipisicing elit.
			Accusamus tempore ipsam reprehenderit beatae totam quas enim iste omnis quibusdam, fuga at,
			rem vero quisquam! Sapiente quos fugit atque saepe eius.Lorem ipsum dolor sit amet consectetur
			adipisicing elit. Accusamus tempore ipsam reprehenderit beatae totam quas enim iste omnis
			quibusdam, fuga at, rem vero quisquam! Sapiente quos fugit atque saepe eius.Lorem ipsum dolor
			sit amet consectetur adipisicing elit. Accusamus tempore ipsam reprehenderit beatae totam quas
			enim iste omnis quibusdam, fuga at, rem vero quisquam! Sapiente quos fugit atque saepe eius.
		</div>
	{/if}
</div>

<div id="ansprechpartner" class="ansprechpartner">
	<h2>IHRE PARTNER</h2>
	<h4>WIR SIND FÜR SIE DA</h4>

	<div class="persons">
		<div class="person">
			<div class="image">
				<picture>
					<source
						srcset="/img/thorsten_hammer.jpg 468w, /img/thorsten_hammer.jpg 936w"
						type="image/webp"
					/>
					<img
						src="/img/thorsten_hammer.jpg"
						srcset="/img/thorsten_hammer.jpg 468w, /img/thorsten_hammer.jpg 936w"
						alt=""
						loading="lazy"
					/>
				</picture>
			</div>
			<h3>Thorsten Hammer</h3>
			<p>Wirtschaftsprüfer, Steuerberater</p>
			<p><a href="tel:+49 421 369 04 50">+49 421 369 04 50</a></p>
			<p><a href="mailto:t.hammer@hammer.partners">t.hammer@hammer.partners</a></p>
			<p><a href="/vcf/t_hammer.vcf" download>vCard herunterladen</a></p>
		</div>
		<div class="person">
			<div class="image">
				<picture>
					<source
						srcset="/img/matthias_henke.jpg 468w, /img/matthias_henke.jpg 936w"
						type="image/webp"
					/>
					<img
						src="/img/matthias_henke.jpg"
						srcset="/img/matthias_henke.jpg 468w, /img/matthias_henke.jpg 936w"
						alt=""
						loading="lazy"
					/>
				</picture>
			</div>
			<h3>Mathias Henke</h3>
			<p>Softwareentwickler</p>
			<p><a href="mailto:m.henke@it-solve-mh.de">m.henke@hammer.partners</a></p>
			<p><a href="/vcf/m_henke.vcf" download>vCard herunterladen</a></p>
		</div>
		<div class="person">
			<div class="image">
				<picture>
					<source
						srcset="/img/oliver_schumacher.jpg 468w, /img/oliver_schumacher.jpg 936w"
						type="image/webp"
					/>
					<img
						src="/img/oliver_schumacher.jpg"
						srcset="/img/oliver_schumacher.jpg 468w, /img/oliver_schumacher.jpg 936w"
						alt=""
						loading="lazy"
					/>
				</picture>
			</div>
			<h3>Oliver Schumacher</h3>
			<p>Wirtschaftsprüfer, Steuerberater</p>
			<p><a href="tel:+49 421 369 04 60">+49 421 369 04 60</a></p>
			<p><a href="mailto:o.schumacher@hammer.partners">o.schumacher@hammer.partners</a></p>
			<p><a href="/vcf/o_schumacher.vcf" download>vCard herunterladen</a></p>
		</div>
	</div>
</div>

<div id="ansprechpartner" class="ansprechpartner">
	<h2>Ein Einblick in unser Team</h2>

	<div class="persons">
		{#each team as person}
			<div class="person">
				<div class="image">
					<picture>
						<source srcset={person.img + ' 468w, ' + person.img + ' 936w'} type="image/webp" />
						<img
							src={person.img}
							srcset={person.img + ' 468w, ' + person.img + ' 936w'}
							alt=""
							loading="lazy"
						/>
					</picture>
				</div>
				<p>{person.name}</p>
			</div>
		{/each}
	</div>
</div>

<style lang="scss">
	@import '$lib/scss/homepage.scss';
</style>
